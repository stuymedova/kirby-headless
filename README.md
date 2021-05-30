# Kirby Headless

For the instructions on how to get started with Kirby, see: [getkirby.com/docs/guide/quickstart](https://getkirby.com/docs/guide/quickstart).

For the KQL Plugin documentation, see: [github.com/getkirby/kql#kirby-ql](https://github.com/getkirby/kql#kirby-ql).

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

## Recreate

1. Download the KQL plugin [manually](https://github.com/getkirby/kql/releases) or with composer: `composer require getkirby/kql`.

KQL adds an API endpoint which can be accessed at `{url}/api/query`. It is read only.

2. The endpoint requires authentication. For more information, see [getkirby.com/docs/guide/api/authentication](https://getkirby.com/docs/guide/api/authentication).

2.1. Create an API user and set user permissions as in [`/site/blueprints/users`](https://github.com/stuymedova/kirby-headless/tree/main/site/blueprints/users). See documentation: [getkirby.com/docs/guide/users/roles](https://getkirby.com/docs/guide/users/roles) and [getkirby.com/docs/guide/users/permissions](https://getkirby.com/docs/guide/users/permissions).

2.2. Set up either Session-based Authentication or Basic Auth. In this setup, I use the latter. To set up Basic Auth, modify [`/site/config/config.php`](https://github.com/stuymedova/kirby-headless/blob/main/site/config/config.php):
```php
return [
  'api' => [
    'basicAuth' => true,
    'allowInsecure' => true # TODO: remove pre-production
  ]
];
```
> “Basic auth is only available over HTTPS to avoid that the credentials are sent over the wire unencrypted with every request. This restriction can be disabled via [the `allowInsecure` option](https://getkirby.com/docs/reference/system/options/api#allow-insecure-requests).”

3. Create an account by going to `{url}/panel`.

4. Create an API user. See [getkirby.com/docs/guide/users/managing-users](https://getkirby.com/docs/guide/users/managing-users). Further use these credentials to authorize requests to your API.

## Quick Setup

1. Clone/download this repository.
2. Run in terminal: 
```shell
composer install
valet link # for Valet users
```
3. Implement steps 3 and 4 above.

## Potentially useful tools
[Insomnia](https://insomnia.rest) (testing)
