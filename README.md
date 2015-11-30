# MinishlinkWebPushBundle

This bundle provides a simple integration of the [WebPush library](https://github.com/Minishlink/web-push).

## Usage
Web Push sends notifications to endpoints which server delivers web push notifications as described in
the [Web Push API specification](http://www.w3.org/TR/push-api/).

```php
<?php
/** @var \Minishlink\WebPush\WebPush */
$webPush = $this->container->get('minishlink_web_push');
```

The bundle provides a new `minishlink_web_push` service that returns an instance of `Minishlink\WebPush\WebPush`.

For more info on what you can do with `$webPush`, check [Minishlink/web-push](https://github.com/Minishlink/web-push).

## Installation

1. `composer require minishlink/web-push-bundle`
2. Enable the bundle in your `app/AppKernel.php`.

```php
<?php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new Minishlink\Bundle\WebPushBundle\MinishlinkWebPushBundle(),
        // ...
    );
}
```

## Configuration
Here is the default configuration, you may change it in your `app/config/config.yml`.

```yml
minishlink_web_push:
  api_keys: # you should put api keys in your "app/config/parameters.yml" file
    GCM: ''
  ttl: null # Time to Live of notifications in seconds
  timeout: 10 # Timeout of each request in seconds
```
