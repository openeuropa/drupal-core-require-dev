# drupal-core-require-dev

[![Build Status](https://drone.fpfis.eu/api/badges/openeuropa/drupal-core-require-dev/status.svg?branch=8.6.x)](https://drone.fpfis.eu/openeuropa/drupal-core-require-dev)
[![Packagist](https://img.shields.io/packagist/v/openeuropa/drupal-core-require-dev.svg)](https://packagist.org/packages/openeuropa/drupal-core-require-dev)

``openeuropa/drupal-core-require-dev`` provides the ``require_dev`` dependencies of ``drupal/core`` as a standalone package. It follows the same release cycle and versioning scheme as Drupal core. You should use the same version constraint for it as you use for Drupal core.

It applies some patches on ``drupal/core`` that are needed for development on OPENEUROPA modules.

## Usage

### Drupal Core 8.6.x

``composer require --dev openeuropa/drupal-core-require-dev ~8.6``

## Installation using Docker Compose

The setup procedure can be simplified by using Docker Compose.

Requirements:

- [Docker](https://www.docker.com/get-docker)
- [Docker-compose](https://docs.docker.com/compose/)

Copy docker-compose.yml.dist into docker-compose.yml.

You can make any alterations you need for your local Docker setup. However, the defaults should be enough to set the project up.

Run:

```
$ docker-compose up -d
```

Then:

```
$ docker-compose exec web composer install
```
