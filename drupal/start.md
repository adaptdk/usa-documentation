# Starting a Drupal project

This is a set of minimal steps to get a Drupal project started.

## What

- [Drupal recommended composer project](https://github.com/drupal/recommended-project)
- [Lando](https://lando.dev)

# Script

```shell
# Prepare with relevant variables.
PROJECT_NAME='your-project'
EMAIL='name@adaptagency.com'
ORIGIN="git@github.com:adaptdk/$PROJECT_NAME.git"

# Get drupal from recommended project.
composer create-project --no-install drupal/recommended-project repository
cd repository
# Start git repository.
git init
git config user.email "$EMAIL"
git remote add origin "$ORIGIN"
git add composer.json composer.lock
git commit -m"Start project $PROJECT_NAME git repository"
# Start lando project.
lando init --name="$PROJECT_NAME" --recipe='drupal9'
git add .lando.yml
git commit -m'Start lando configuration'
lando composer install
# TODO Continue.
```
