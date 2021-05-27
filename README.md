# Kirby Headless

## Reproduce

1. Run in terminal:
```shell
composer i
composer require getkirby/kql
valet link # for Valet users
```

2. Modify `config.php`:
```php
return [
  'api' => [
    'basicAuth' => true,
    'allowInsecure' => true # dev only
  ]
];
```

3. Install the Panel 
4. Create an API user
