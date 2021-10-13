# Drupal 8 to 9

A general draft on upgrading Drupal 8 to 9.
Some documentation about this is available at drupal.org [Upgrading from Drupal
8 to Drupal 9 (or
later)](https://www.drupal.org/docs/upgrading-drupal/upgrading-from-drupal-8-to-drupal-9-or-later).

## Approach

Strive for doing the less amount of needed changes to get the upgrade done.

It is easy to change directions in the process, so it is important to keep the goal in mind.
There is always opportunity to do extra non-required steps at the end.

## Process overview

Details may vary, but this may be a good starting set of steps.
These instructions assume a direct upgrade of a single installation site, changing as less behavior as possible.
Includes some hints about fixing status first, since code may have not been created by us.

1. Setup the local site, e.g. with lando.
1. Make sure database updates are at the latest state.
1. Make sure configuration export does not generate changes, for the usual case when configuration is tracked on git.
1. Make sure there are no pending Drupal 8 security upgrades for Drupal core or contributed modules.
   If there are some, install and deploy them first.
1. Make sure the project is using `drupal/core-recommended`, which is the suggested way to track drupal dependencies, change to it if needed.
1. Install [upgrade_status](https://www.drupal.org/project/upgrade_status) module locally, excluding it from configuration exports.
   E.g. `$settings['config_exclude_modules'] = ['upgrade_status'];` on your `settings.local.php`.
1. Remove modules in the codebase that are not installed on the site or not planned to be used.
1. Upgrade contributed modules not compatible with Drupal 9 to a latest available version that supports Drupal 9.
1. Run the `upgrade_status` check for custom modules, and change its code to be compatible with Drupal 9 if needed.
1. Investigate, evaluate, and upgrade contributed modules without a Drupal 9 compatible version.
   This can be a really consuming step if there are multiple or the contributed modules are complex.
1. Upgrade drupal core and related dependencies.
1. Evaluate Drupal 9 infrastructure requirements are met on the production environment, and deploy.

## One module upgrade

A given module upgrade is likely close to the following steps.

1. Identify the changes on new releases at drupal.org, they may need some manual intervention in major version jumps.
1. Change the version constraint if needed on `composer.json`.
1. Run the upgrade along with dependencies, e.g. `lando composer update --with-all-dependencies drupal/modulename`.
1. Run database updates, e.g. `lando drush updb`.
1. Export configuration back into code that may have been changed on updates, and commit them, e.g. `lando drush cex`.
1. Verify its functionality is still in place on the site.

## Composer 2

It is likely that the site was using composer 1 with drupal 8.x.
This is especially true when using drupal/core-dev, which pins a composer
version.

During this upgrade, composer plugins need to be compatible with composer 2
before the upgrade; hence, in the same way than with modules, updating to a
recent version with compatibility for the new version is the first step.

Also, several of them may just need to be removed.

See [Preparing your site for Composer 2](https://www.drupal.org/docs/develop/using-composer/preparing-your-site-for-composer-2).

## Other notes

- Gather production names and versions of infrastructure software: web server, php version, other services in use.
- Be sure that you are using the composer version at the `composer.lock`, so keep changes as minimal as possible there.
