# Bootstrap-BP hugo theme

[Bootstrap v4](https://getbootstrap.com/) based Hugo theme which provides out of the box best practices like performance and SEO readiness. Featured images will be resized automatically. This is based on the [Hugo docs](https://gohugo.io/templates/homepage/), [hugo-best-practices](https://github.com/spech66/hugo-best-practices), [Front-End Checklist](https://github.com/thedaviddias/Front-End-Checklist) and the [Front-End Performance Checklist](https://github.com/thedaviddias/Front-End-Performance-Checklist). Contains four different color themes.

## Install the theme

With Git installed, run the following commands inside the Hugo site folder. If Hugo has not yet been installed, read the setup guide [here](https://gohugo.io/overview/installing/).

```sh
mkdir themes
cd themes
git clone https://github.com/spech66/bootstrap-bp-hugo-theme.git
```

You can get a zip of the latest version of the theme from the [home page](https://github.com/spech66/bootstrap-bp-hugo-theme) and extract it to the themes folder.

## Theme settings

Most settings should be done with hugo specific variables. There are only a few (optional) additional `[params]`.

* `startPageColumns = true` will show the start page in a Masonry-like mode.
* `customDateFormat` to override the date format.
* `showListsGrouped` to add headers for every year.
* `showPostSummary` only show a summary on index and lists.
* `colorTheme` set to dark, light, blue (do not set for bootstrap default)

![startPageColumns = true](https://raw.githubusercontent.com/spech66/bootstrap-bp-hugo-theme/master/images/tn.png)

![startPageColumns = false](https://raw.githubusercontent.com/spech66/bootstrap-bp-hugo-theme/master/images/tn2.png)

## Google Analytics

This theme uses the internal asynchronous template for Google Analytics tracking. You only have to provide your tracking id in your configuration file:

```yaml
googleAnalytics = "UA-123-45"
```

## Schema.org support

Provide one author to enable the Schema.org support.

```yaml
[Author]  
  name = "Sebastian Pech"
```

## Images, Open Graph and Twitter Cards

This theme uses Hugos `feature/cover` name method to set the optimized feature image. The image named `*feature*` or `*cover*` is used for the posts featured image and get resized. This will also be in the Twitter Cards and Open Graph block.

The header image is automatically added if there is a file called `*feature*` or `*cover*`. The first wildcard is prefered over the second one. If there are multiple images the first one is used.

```yaml
# Site Config toml
title = "My hugo site"

[params]
  description = "Text about the site"

# Post yaml
---
title: "{{ replace .Name "-" " " }}"
date: {{ .Date }}
publishdate: {{ now.Format "2006-01-02" }}
lastmod: {{ now.Format "2006-01-02" }}
draft: true
description: "Text about this post"
tags:
    - "tag 1"
---
```

## Menus

There are two menus in the theme. `main` and `footer`. Specify the entries in the config or the header of the content.

```yaml
[menu]

  [[menu.main]]
    identifier = "about"
    name = "About"
    url = "/about/"
    weight = 10

  [[menu.footer]]
    identifier = "Imprint"
    name = "Imprint"
    url = "/imprint/"
    weight = 10
```

```yaml
---
[...]
menu = "main"
---
```

## Social Icons
Icons for socialmedia. Add to config.

```yaml
# Sets Social Media icons to appear and link to your account. Value should be your
# username unless otherwise noted.
# Code from https://themes.gohugo.io/future-imperfect/ theme
[social]
  # Coding Communities
  github           = "a"
  gitlab           = "a"
  stackoverflow    = "a" # User Number
  bitbucket        = "a"
  jsfiddle         = "a"
  codepen          = "a"
  # Visual Art Communities
  deviantart       = "a"
  flickr           = "a"
  behance          = "a"
  dribbble         = "a"
  # Publishing Communities
  wordpress        = "a"
  medium           = "a"
  # Professional/Business Oriented Communities
  linkedin         = "a"
  linkedin_company = "a"
  foursquare       = "a"
  xing             = "a"
  slideshare       = "a"
  # Social Networks
  facebook         = "flowartsde" # https://fb.me/flowartsde
  googleplus       = "a"
  reddit           = "a"
  quora            = "a"
  youtube          = "/channel/UCmWkMX_QkSLxxEDT-A1gu3w" # https://www.youtube.com/channel/UCmWkMX_QkSLxxEDT-A1gu3w
  vimeo            = "a"
  whatsapp         = "a" # WhatsApp Number
  instagram        = "flowartsde" # https://www.instagram.com/flowartsde/
  tumblr           = "a"
  twitter          = "a"
  skype            = "a"
  snapchat         = "a"
  pinterest        = "a"
  telegram         = "a"
  # Email
  email            = "a"
```
