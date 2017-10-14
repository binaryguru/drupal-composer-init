# drupal-composer-init

[![Latest Version](https://img.shields.io/github/release/hussainweb/drupal-composer-init.svg?style=flat-square)](https://github.com/hussainweb/drupal-composer-init/releases)
[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)
[![Build Status](https://img.shields.io/travis/hussainweb/drupal-composer-init/master.svg?style=flat-square)](https://travis-ci.org/hussainweb/drupal-composer-init)
[![Total Downloads](https://img.shields.io/packagist/dt/hussainweb/drupal-composer-init.svg?style=flat-square)](https://packagist.org/packages/hussainweb/drupal-composer-init)

This plugin provides a new composer command (`drupal-init`) which helps in creating new Drupal installations based on composer. Most of the options are very similar to the default `composer init` command. There are additional options to specify a Drupal core or distro to use and the docroot.

This plugin also supports Drupal 7 installation but this option needs to be passed in from command line.

## Installation

Since this plugin provides a new composer command that should be used in an empty directory (or at least a directory without a composer.json setup), this has to be installed globally.

```
composer global require hussainweb/drupal-composer-init:~1.0
```

## Updating

```
composer global update hussainweb/drupal-composer-init --with-dependencies
```

## Usage

In a fresh directory, run this command to get started.

```
composer drupal-init
```

To intialise a Drupal 7 website, run the following command:

```
composer drupal-init --drupal-7
```

### Specifying extensions (modules, themes, profiles)

Drupal extensions such as modules, themes, and profiles can be specified in the regular `require` or `require-dev` section of composer.json schema.

All Drupal extensions can be specified in the regular packages section with their drupal.org name prefixed by '`drupal/`'. For example, if you want to require panels module, specify `drupal/panels`.

```
Define your dependencies.

Would you like to define your dependencies (require) now [yes]?
Search for a package: drupal/panels
Enter the version constraint to require (or leave blank to use the latest version):
Using version ^4.2 for drupal/panels
Search for a package: drupal/redirect
Enter the version constraint to require (or leave blank to use the latest version):
Using version ^1.0@beta for drupal/redirect
Search for a package:
```

### Additional Help

Run `composer help drupal-init` for more options.

```
Usage:
  drupal-init [options]

Options:
      --name=NAME                Name of the package
      --description=DESCRIPTION  Description of package
      --author=AUTHOR            Author name of package
      --type[=TYPE]              Type of package (e.g. library, project, metapackage, composer-plugin) [default: "project"]
      --homepage=HOMEPAGE        Homepage of package
      --require=REQUIRE          Package to require with a version constraint, e.g. foo/bar:1.0.0 or foo/bar=1.0.0 or "foo/bar 1.0.0" (multiple values allowed)
      --require-dev=REQUIRE-DEV  Package to require for development with a version constraint, e.g. foo/bar:1.0.0 or foo/bar=1.0.0 or "foo/bar 1.0.0" (multiple values allowed)
  -c, --core=CORE                Drupal Core or distribution, e.g. drupal/core or acquia/lightning [default: "drupal/core"]
  -s, --stability=STABILITY      Minimum stability (empty or one of: stable, RC, beta, alpha, dev)
  -l, --license=LICENSE          License of package
      --repository=REPOSITORY    Add custom repositories, either by URL or using JSON arrays (multiple values allowed)
  -w, --web-dir=WEB-DIR          Specify the docroot (defaults to web) [default: "web"]
      --drupal-7                 Use Drupal 7 packagist instead of Drupal 8
  -h, --help                     Display this help message
  -q, --quiet                    Do not output any message
  -V, --version                  Display this application version
      --ansi                     Force ANSI output
      --no-ansi                  Disable ANSI output
  -n, --no-interaction           Do not ask any interactive question
      --profile                  Display timing and memory usage information
      --no-plugins               Whether to disable plugins.
  -d, --working-dir=WORKING-DIR  If specified, use the given directory as working directory.
  -v|vv|vvv, --verbose           Increase the verbosity of messages: 1 for normal output, 2 for more verbose output and 3 for debug

Help:
  The drupal-init command creates a composer.json file
  usable for Drupal projects in the current directory.

  php composer.phar drupal-init
```

## Contributing

Contributions are welcome. Please use the issue queue to describe the problem. Pull requests are welcome.
