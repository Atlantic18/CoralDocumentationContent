<span id="philosophy"></span>

**Coral** was built based on a strange idea that I have been coming to for several years. Although it may sound very illogical I came to conclusion that:

> If you want to do something really nice for business users do not give them Content Management System

From my early days in IT I've been either working with or developing a CMS. I'm not saying that current CMS platforms are bad and in many cases they are quite the opposite. But I during my career I faced many use cases where it didn't make much sense to use them.

When Symfony platform was introduced I started to like it a lot and all of my projects were based mainly on Symfony. Logically I tried to add content management functionality to the projects. Sometimes these projects were portals, sometime projects with pretty complex business logic and sometime product pages or some sort of e-commerce. In the end in every project there was a need for static content: e.g. product description, help pages, news or blog posts.

None of my attempts was satisfactory and I got annoyed with the platform after months or years. I realized that **most of the time I'm trying to bend the CMS platform so I can do something the platform can't do**. The reason for these failed attempts was that the CMS platform was the center piece and the business logic was added on top of it. It would be nice if I could tell that it took me short time to see the glitch but it was quite a long time before I saw I need to change the approach.

Finally we're getting back to **Coral**. Its architecture was designed based on this knowledge. Following principles were applied:

- Your project is the central piece and Coral is here to bring the content in
- Coral is light, very light, one could even say it can't do much
- It will remain like this forever
- It's developed as a set of Symfony bundles but the idea can be implemented in almost any other language/framework

There is much more if you deep dive into the architecture and hopefully you find this to be the missing piece in you software stack.


<span id="architecture"></span>

## Architecture



## No database

<span id="git-flow"></span>

## Content Git-flow
