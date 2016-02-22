Start with a fresh [symfony project](http://symfony.com/doc/current/book/installation.html) or existing one. Example how to start:

```shell
$ sudo curl -LsS https://symfony.com/installer -o /usr/local/bin/symfony
$ sudo chmod a+x /usr/local/bin/symfony
$ symfony new coral_demo
```

Update composer.json to reflect necessary dependencies **coral/core-bundle** and **coral/site-bundle**:

```javascript
{
    /* Standard parts of composer.json .... */
    "require": {
        "php": ">=5.3.3",
        "symfony/symfony": "~2.8",
        "twig/extensions": "~1.0",
        "symfony/assetic-bundle": "~2.4",
        "symfony/swiftmailer-bundle": "~2.3",
        "symfony/monolog-bundle": "~2.8",
        "sensio/distribution-bundle": "~3.0",
        "sensio/framework-extra-bundle": "~3.0",
        "incenteev/composer-parameter-handler": "~2.0",
        "coral/core-bundle": ">=0.2",
        "coral/site-bundle": ">=0.3"
    },
    /* Standard parts of composer.json .... */
}
```

It's advisable to start with some sample data so you can learn on the go. You can fetch this [site content from Github](https://doplnit) to help you start:

```shell
$ wget s githubu a uložení do cesty

doplnit
```

And run composer update (you'll be asked to configure following parameters):

```shell
$ composer update

doplnit parametry a cestu s githubem
```

Following steps might vary depending on your setup but if you've used symfony installer as described in the first step you can follow with:

```shell
$ php bin/console server:run command.
```

Now you can browse to the [http://localhost:8000/documentation/installation](http://localhost:8000/documentation/installation).