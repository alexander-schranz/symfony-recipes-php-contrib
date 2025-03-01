# Symfony Recipes using PHP Config Files

This repository provides [symfony/recipes](https://github.com/symfony/recipes)
using `PHP` instead of YAML files.

The project is using [symplify/config-transformer](https://github.com/symplify/config-transformer)
to convert the `.yaml` config files to `.php` config files. To make 100%
sure you are getting the same recommendation as the official recipes provides.

A big thank you to [TomasVotruba](https://github.com/TomasVotruba) for providing the `symplify/config-transformer`
package and fixing a lot of issues without this project would not be possible.

The converter can be found in the [alexander-schranz/symfony-recipes-yaml-to-php-converter](https://github.com/alexander-schranz/symfony-recipes-yaml-to-php-converter)
repository.

## Skeletons

There are currently also 2 skeletons shipped which can be used to create new symfony projects:

**symfony/skeleton clone:**

[schranz/symfony-php-skeleton](https://github.com/alexander-schranz/symfony-php-skeleton):

```bash
composer create-project schranz/symfony-php-skeleton
```

**symfony/website-skeleton clone:**

[schranz/symfony-php-website-skeleton](https://github.com/alexander-schranz/symfony-php-website-skeleton):

```bash
composer create-project schranz/symfony-php-website-skeleton
```

## Using in exist projects

First convert your project with [symplify/config-transformer](https://github.com/symplify/config-transformer) from `.yaml` to `.php` configs
after add the following to the `composer` `extra.symfony.endpoint` configuration:

```json
    "extra": {
        "symfony": {
            "allow-contrib": false,
            "require": "6.1.*",
            "endpoint": [
                "https://raw.githubusercontent.com/alexander-schranz/symfony-recipes-php/flex/main/index.json",
                "https://raw.githubusercontent.com/alexander-schranz/symfony-recipes-php-contrib/flex/main/index.json",
                "flex://defaults"
            ]
        }
    }
```

### Contributing

Update recipes manually:

```bash
composer install

vendor/bin/yaml-to-php git@github.com:symfony/recipes-contrib.git
```
