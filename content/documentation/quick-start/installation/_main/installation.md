Start with a fresh [symfony project](http://symfony.com/doc/current/book/installation.html) or existing one. Example how to start:

```shell
$ sudo curl -LsS https://symfony.com/installer -o /usr/local/bin/symfony
$ sudo chmod a+x /usr/local/bin/symfony
$ symfony new coral_demo
```

Update ```composer.json``` to reflect necessary dependencies **coral/core-bundle** and **coral/site-bundle**:

```javascript
{
    /* Standard parts of composer.json .... */
    "require": {
        ....
        "coral/core-bundle": ">=0.2",
        "coral/site-bundle": ">=0.3"
    },
    /* Standard parts of composer.json .... */
}
```

And activate bundles in ```app/AppKernel.php```:

```php
class AppKernel extends Kernel
{
    public function registerBundles()
    {
        $bundles = [
            ....
            //Coral Bundles
            new Knp\Bundle\MarkdownBundle\KnpMarkdownBundle(),
            new Coral\CoreBundle\CoralCoreBundle(),
            new Coral\SiteBundle\CoralSiteBundle()
        ];

        ....
    }
}
```

Update ```app/config/config.yml``` with the minimum coral configuration:

```yml
coral_site:
    content_path: %coral_content%
    config_path: %coral_config%

knp_markdown:
    parser:
        service: markdown.parser.flavored

# Add also to twig configuration additional path and add services to globals
twig:
    paths:
        "%coral_content%": coral
    globals:
        page:         "@coral.page"
        renderer:     "@coral.renderer"
```

Update ```app/config/config_dev.yml``` with in memory caching:

```yml
parameters:
    coral.site_cache.class:    Doctrine\Common\Cache\ArrayCache
    coral.connect_cache.class: Doctrine\Common\Cache\ArrayCache
```

Update ```app/config/paramters.yml.dist``` with default parameters:

```yml
parameters:
    coral_content: Default Content Path (e.g. /var/www/CoralDocumentationContent/content)
    coral_config:  Default Config Path (e.g. /var/www/CoralDocumentationContent/configuration)
```

It's advisable to start with some sample data so you can learn on the go. You can fetch this [site content from Github](https://github.com/Atlantic18/CoralDocumentationContent) to help you start:

```shell
$ git clone https://github.com/Atlantic18/CoralDocumentationContent.git
```

Run composer update (you'll be asked to configure coral parameters). Fill appropriate paths:

```shell
$ composer update
```

Update ```app/Resources/views/base.html.twig``` and add at least following twig code:

```shell
<body>
    {% block header %}{% endblock %}

    {% block main %}{% endblock %}

    {% block footer %}{% endblock %}

    {% block assets %}{% endblock %}
</body>
```

Following steps might vary depending on your setup but if you've used symfony installer as described in the first step you can follow with:

```shell
$ php bin/console server:run command.
```

Now you can browse to the [http://localhost:8000/documentation/quick-start/installation](http://localhost:8000/documentation/quick-start/installation). Enjoy and don't be surprised about the missing styles and images. This is where your work starts...