## Node

Coral content has a tree structure so a node represents each item within this tree. Node can be usually accessed via a URL and is also represented as a folder on your drive:

```
/about
/documentation
    /content
        /basics
        /filters
    /properties
        /basics
        /built-in
    /quick-start
        /installation
        /guide
/license
/phylosophy
```

Coral Node has Properties and Areas (with Content).

## Area

Area is a placeholder within a template where Coral Content is rendered:

```twig
{% extends '::base.html.twig' %}

{% block title %}{{ page.node.name }}{% endblock %}
{% block description %}{{ page.node.getProperty('meta_description') }}{% endblock %}

{% block header %}
    {{ include('CoralSiteBundle:Default:area.html.twig', { 'name': 'header', 'page': page, 'renderer': renderer }) }}
{% endblock %}

{% block main %}
    <section class="main">
        {{ include('CoralSiteBundle:Default:area.html.twig', { 'name': 'main', 'page': page, 'renderer': renderer }) }}
    </section>
{% endblock %}

{% block footer %}
    {{ include('CoralSiteBundle:Default:area.html.twig', { 'name': 'footer', 'page': page, 'renderer': renderer }) }}
{% endblock %}

{% block assets %}
    {{ include('CoralSiteBundle:Default:area.html.twig', { 'name': 'assets', 'page': page, 'renderer': renderer }) }}
{% endblock %}
```

In the above example you can see 4 areas defined: header, main, footer and assets. Naming of area tells Coral where to look for content in the structure _(on the drive area is a folder where content is stored)_. More about this in [Content/Basics](/documentation/content/basics).

## Content

Each area can contain multiple Contents _(on the drive a content is a file within the Area folder)_. There are several Content types supported via **Content filters** which render Content based on their type. Content of type .connect _(a file with extension .connect)_ might look similar to this one:

```json
{
    "service":  "coral",
    "method":   "GET",
    "uri":      "/v1/node/detail/published/config-logger",
    "template": "@coral/.main/_connect_custom_template.twig",
    "variables": {
        "foo":  "bar",
        "foo2": "bar2"
    }
}
```

Connect filter is one of the more complicated ones to understand from the beginning. So the simplest one is Passthru filter which render exactly what's placed in a file e.g. sample.html:

```html
<p>Lorem ipsum</p>
```

## Property

Each Node can have unlimited number of properties. There's a number of built-in properties: e.g. redirection, permission control, template configuration. On top of these properties you can assign any property that you can later on use either in the Template or Controller. Sample property configuration:

```text
Lightweight Web Platform

template: @coral/_templates/homepage.html.twig
keywords:"Skipper, Doctrine, Doctrine2, Propel, CakePHP, ORM, definitions"
description:"Skipper help site"
```