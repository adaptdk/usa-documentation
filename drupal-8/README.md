## Managing Configuration

If you're brand new to the configuration management system in D8, please refer to the [official overview](https://www.drupal.org/docs/8/configuration-management/managing-your-sites-configuration) in order to pick the basic concepts.

Another important concept to understand is what is considered [configuration vs content](https://www.drupal.org/docs/8/api/configuration-api/overview-of-configuration-vs-other-types-of-information).

### Recommended Workflow

- Begin work on new ticket
- Branch from latest version of `develop` branch
- `drush cim -y` to bring any upstream config changes from the file system into your local database. This ensures you're starting from a clean slate.
- Make changes to site configuration, either via the UI or by installing a new module
- `drush cex -y` exports those changes to the filesystem, where you then commit them to git
- It's recommended to organize your configuration updates into coherent chunks. For instance, if you enable a module and then make some unrelated configuration changes to a content type, you should split those updates into 2 commits. The easiest way to do that is to make the first change, export + commit, then start the second change.

### Gotchas

- `drush cim` + `drush cex` are destructive, all or nothing actions. If you have configuration that you wish to keep in your database, but have not yet exported it to the file system via `drush cex`, running `drush cim` will destroy that work. `drush cex` is less troublesome because we version control our configuration in git, so any mistakes you make can easily be reverted.
- Merge conflicts are likely to happen with configuration files, especially at the beginning of a project when site building is happening simultaneously. Resolving them is a judgement call you have to make depending on the situation. If you are not confident in how to fix the conflict, the best way may be to blow away your changes via `drush cim` and start from scratch.