# drupal-core-require

[![Build Status](https://drone.fpfis.eu/api/badges/openeuropa/drupal-core-require-dev/status.svg?branch=8.6.x)](https://drone.fpfis.eu/openeuropa/drupal-core-require-dev)

``openeuropa/drupal-core-require-dev`` provides the ``require`` dependencies of ``drupal/core`` as a standalone package. It follows the same release cycle and versioning scheme as Drupal core. You should use the same version constraint for it as you use for Drupal core.

It applies some patches on ``drupal/core`` that are needed on OPENEUROPA modules.

## Usage

### Drupal Core 8.6.x

``composer require --dev openeuropa/drupal-core-require-dev 8.6.0-alpha1``