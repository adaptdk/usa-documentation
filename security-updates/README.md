Security Updates
----------------


## Using drush to find security updates

Drush can be used to find security updates by running

```
drush pm:security
```


## Commit structure

Security updates should be committed per module or plugin, when possible,
and with context in the commit message about the previous and current version.
This helps to ensure that reviewers know exactly what actions have been
taken.  If a bug crops up in the future, the developer will be able to easily
get the context of what changes were introduced, and if necessary can revert the
specific commit that changed the updated module.

As modules, plugins, or core are updated, they should be committed with the
structure: `ISSUE_NUMBER: Update MODULE_NAME from PREVIOUS_VERSION to CURRENT_VERSION.`.
In practice, that may look like the following:

```
#5: Update feeds from 7.x-2.12 to 7.x-2.15.
```

While the example above is for a Drupal 7 module, this can work for Drupal 8 modules
if the updates are done with composer for each separate module.  Eg:

```
composer update --with-dependencies drupal/redirect
git add .
git commit -m "#5: Update redirect from 8.x-1.2 to 8.x-1.5."
composer update --with-dependencies ...
```
