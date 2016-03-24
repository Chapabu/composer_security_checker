# Composer Security Checker

## Introduction

The Composer Security Manager module will check any installed Composer packages
against using the [SensioLabs Security Checker](https://security.sensiolabs.org/)
service, and output a report similar to the core Update Manager report.

## Installation

### With Composer Manager

The Composer Security Checker module ships with a `composer.json` file.
Provided Composer Manager has been configured correctly, when you enable
Composer Security Checker, it _should_ just work.

### Without Composer Manager

Due to the nature of Drupal 8, it's not necessarily required to have Composer
Manager installed to benefit from Composer.

If you are not using Composer Manager, but you are using Composer packages,
then you will need to do the following:

1. Add the following to the `composer.json` file found in your Drupal root.

``` language-json
"sensiolabs/security-checker": "3.0.*",
```

2. Run `composer install`

## Roadmap

These are just some things I'd like to get in at some point. There is no
timescale for their implementation.

* Cache the response based on the hashes in the `composer.lock` file.
* Add e-mail notifications.
* Add documentation for service switching.

## Contribution

As this module is pretty much solely API based, testing is tricky. Any patches
submitted moving forward that don't have direct contact with the SensioLabs
should contain PHPSpec specs. These specs do not follow Drupal Coding
Standards, so if contributing, please ensure the standards as set out in the
spec files is matched.

To run the PHPSpec tests, run `composer install` in the module directory,
and then run `./vendor/bin/phpspec run`.
