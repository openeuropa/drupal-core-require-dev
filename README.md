# drupal-core-require-dev

[![Build Status](https://drone.fpfis.eu/api/badges/openeuropa/drupal-core-require-dev/status.svg?branch=8.6.x)](https://drone.fpfis.eu/openeuropa/drupal-core-require-dev)
[![Packagist](https://img.shields.io/packagist/v/openeuropa/drupal-core-require-dev.svg)](https://packagist.org/packages/openeuropa/drupal-core-require-dev)

``openeuropa/drupal-core-require-dev`` provides the ``require-dev`` dependencies of ``drupal/core`` as a standalone package. It follows the same release cycle and versioning scheme as Drupal core. You should use the same version constraint for it as you use for Drupal core.

It applies some patches on ``drupal/core`` that are needed for development on OPENEUROPA modules.

## Patches list

- [Patch](https://www.drupal.org/files/issues/2018-07-05/2943172-kernel-test-base-3.patch) for issue [#2943172](https://www.drupal.org/project/drupal/issues/2943172) -
Directories can't be ignored when collecting extensions during PHPUnit tests.
Symlinks inside the Drupal testing instance result in infinite loops.
- [Patch](https://www.drupal.org/files/issues/2019-03-01/2599228-131.patch) for issue [#2599228](https://www.drupal.org/project/drupal/issues/2599228) -
Programmatically created translatable content type returns SQL error on content creation.
- [Patch](https://www.drupal.org/files/issues/outbound_http_requests-2571475-10.patch) for issue [#2571475](https://www.drupal.org/project/drupal/issues/2571475) -
Outbound HTTP requests fail with KernelTestBase (TNG).
- [Patch](https://www.drupal.org/files/issues/2019-03-14/2600154-rerolling_patch_for_8.6-68.patch) for issue [#2600154](https://www.drupal.org/project/drupal/issues/2600154) -
Deprecation warnings in Twig code cause test failures.

## Usage

### Drupal Core 8.6.x

``composer require --dev openeuropa/drupal-core-require-dev ~8.6``

## Installation using Docker Compose

The setup procedure can be simplified by using Docker Compose.

Requirements:

- [Docker](https://www.docker.com/get-docker)
- [Docker-compose](https://docs.docker.com/compose/)

Run:

```bash
docker-compose up
```

Then:

```bash
docker-compose exec web composer install
```
