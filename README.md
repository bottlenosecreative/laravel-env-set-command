# Laravel `set:env` Command 
## forked from [imliam/laravel-env-set-command](https://github.com/imliam/laravel-env-set-command)

[![Latest Version on Packagist](https://img.shields.io/packagist/v/imliam/laravel-env-set-command.svg)](https://packagist.org/packages/imliam/laravel-env-set-command)
[![Total Downloads](https://img.shields.io/packagist/dt/imliam/laravel-env-set-command.svg)](https://packagist.org/packages/imliam/laravel-env-set-command)
[![License](https://img.shields.io/github/license/imliam/laravel-env-set-command.svg)](LICENSE.md)

## Reason for Fork

This fork was created so I could store/view historic changes to the .env file for debugging purposes. This allows admins/developers to track what env keys were modified, and when they were modified. 

Instead of outright replacing the old key/value pair in the .env file, instead we comment out the previous line, append a timecode of when it was modified, and add the new key/value pair below.

To enable history, add the following to your .env:

```
ENVSET_HISTORY=true
```

env example:

![Env file example](https://bottlenosecreative.com.au/wp-content/uploads/2020/05/set-env-example.jpg "Env file example")


## Original Readme:

Set a .env file variable from the command line.

<!-- TOC -->

- [Laravel `set:env` Command](#laravel-setenv-command)
    - [Installation](#installation)
    - [Usage](#usage)
    - [Changelog](#changelog)
    - [Contributing](#contributing)
        - [Security](#security)
    - [Credits](#credits)
    - [License](#license)

<!-- /TOC -->

## Installation

You can install the package with [Composer](https://getcomposer.org/) using the following command:

```bash
composer require imliam/laravel-env-set-command:^1.0.0
```

## Usage

When running the `env:set` artisan command, you must provide both a key and value as two arguments.

```bash
$ php artisan env:set app_name Example
# Environment variable with key 'APP_NAME' has been changed from 'Laravel' to 'Example'
```

You can also set values with spaces by wrapping them in quotes.

```bash
$ php artisan env:set app_name "Example App"
# Environment variable with key 'APP_NAME' has been changed from 'Laravel' to '"Example App"'
```

The command will also create new environment variables if an existing one does not exist.

```bash
$ php artisan env:set editor=vscode
# Environment variable with key 'EDITOR' has been set to 'vscode'
```

Instead of two arguments split by a space, you can also mimic the `.env` file format by supplying `KEY=VALUE`.

```bash
$ php artisan env:set app_name=Example
# Environment variable with key 'APP_NAME' has been changed from 'Laravel' to 'Example'
```

The command will do its best to stop any invalid inputs.

```bash
$ php artisan env:set @pp_n@me Laravel
# Invalid environment key. Only use letters and underscores
```

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

### Security

If you discover any security related issues, please email liam@liamhammett.com instead of using the issue tracker.

## Credits

- [Liam Hammett](https://github.com/imliam)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
