# drupal-core-require-dev

[![Build Status](https://drone.fpfis.eu/api/badges/openeuropa/drupal-core-require-dev/status.svg?branch=8.8.x)](https://drone.fpfis.eu/openeuropa/drupal-core-require-dev)
[![Packagist](https://img.shields.io/packagist/v/openeuropa/drupal-core-require-dev.svg)](https://packagist.org/packages/openeuropa/drupal-core-require-dev)

``openeuropa/drupal-core-require-dev`` provides the ``require-dev`` dependencies of ``drupal/core`` as a standalone package. It follows the same release cycle and versioning scheme as Drupal core. You should use the same version constraint for it as you use for Drupal core.

It applies some patches on ``drupal/core`` that are needed for development on OPENEUROPA modules.\

## Patches list

- [Patch](https://www.drupal.org/files/issues/2021-01-27/2943172-kernel-test-base-60.patch) for issue [#2943172](https://www.drupal.org/project/drupal/issues/2943172) -
Directories can't be ignored when collecting extensions during PHPUnit tests.
Symlinks inside the Drupal testing instance result in infinite loops.
- [Patch](https://www.drupal.org/files/issues/outbound_http_requests-2571475-10.patch) for issue [#2571475](https://www.drupal.org/project/drupal/issues/2571475) -
Outbound HTTP requests fail with KernelTestBase (TNG).

## Usage

### Drupal Core 8.9.x

``composer require --dev openeuropa/drupal-core-require-dev ~8.9``

## Installation using Docker Compose

The setup procedure can be simplified by using Docker Compose.

Requirements:

- [Docker](https://www.docker.com/get-docker)
- [Docker-compose](https://docs.docker.com/compose/)

The default `docker-compose.yml` file should be enough to set the project up.

Run:

```
$ docker-compose up -d
```

You can make any alterations you need for your local Docker setup, creating a new file `docker-compose.local.yml` with the alterations.

Run:

```
$ docker-compose -f docker-compose.yml -f docker-compose.local.yml up -d
```

Then:

```
$ docker-compose exec web composer install
```

#### Step debugging

To enable step debugging from the command line, pass the `XDEBUG_SESSION` environment variable with any value to
the container:

```bash
docker-compose exec -e XDEBUG_SESSION=1 web <your command>
```

Please note that, starting from XDebug 3, a connection error message will be outputted in the console if the variable is
set but your client is not listening for debugging connections. The error message will cause false negatives for PHPUnit
tests.

To initiate step debugging from the browser, set the correct cookie using a browser extension or a bookmarklet
like the ones generated at https://www.jetbrains.com/phpstorm/marklets/.
