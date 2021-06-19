# Kirby Headless

For instructions on how to get started with Kirby, see [getkirby.com/docs/guide/quickstart](https://getkirby.com/docs/guide/quickstart).  
For KQL Plugin documentation, see [github.com/getkirby/kql](https://github.com/getkirby/kql#kirby-ql).

## Overview

```
.
└── site
    ├── blueprints
    │   └── users
    │       ├── api.yml
    │       └── default.yml
    ├── config
    │   └── config.php
    └── plugins
        └── kql
```

## Prerequisites

[PHP](https://www.php.net) and [Composer](https://getcomposer.org)

## Replicate

Assuming the official [Plainkit](https://github.com/getkirby/plainkit) or [Starterkit](https://github.com/getkirby/starterkit) as a starting point.
1. Install Kirby dependencies: `composer install`.
2. Install the KQL plugin: `composer require getkirby/kql`.
3. Set up authentication: 
* Create an API user and set user permissions in `/site/blueprints/users`. For more information, see documentation on [roles](https://getkirby.com/docs/guide/users/roles) and [permissions](https://getkirby.com/docs/guide/users/permissions).
* Set up Basic Auth. Modify `/site/config/config.php`:
```php
return [
  'api' => [
    'basicAuth' => true,
    'allowInsecure' => true # TODO: remove pre-production
  ]
];
```
4. Startup a local PHP server: `composer start` (or use an alternative: [Laravel Valet/MAMP/…](https://getkirby.com/docs/cookbook/setup/development-environment)).
5. Go to the Panel (`{url}/panel`) and [create an API user](https://getkirby.com/docs/guide/users/managing-users). Further, use these credentials to authorize requests to your API.

## Quick Setup

1. Clone/download this repository.
2. Run in terminal: 
```shell
composer install
composer start
```
3. Implement step 3 above.

## Potentially useful tools
[Insomnia](https://insomnia.rest) (testing)
