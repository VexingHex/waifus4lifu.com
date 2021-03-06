# [Alembic](https://alembic.darn.es/)
[![Gem Version](https://badge.fury.io/rb/alembic-jekyll-theme.svg)](https://badge.fury.io/rb/alembic-jekyll-theme)

⚗ A Jekyll boilerplate theme designed to be a starting point for any Jekyll website.

![Screenshot](https://raw.githubusercontent.com/daviddarnes/alembic/master/screenshot.png)

## Contents
- [About](#about)
- [Features](#features)
- [Examples](#examples)
- [Installation](#installation)
- [Configuration](#configuration)
  - [Gem dependency settings](#gem-dependency-settings)
  - [Site settings](#site-settings)
  - [Site navigation](#site-navigation)
- [Using includes](#using-includes)
- [Page layouts](#page-layouts)
- [Page and Post options](#page-and-post-options)
- [Credits](#credits)

## About

Alembic is a starting point for [Jekyll](https://jekyllrb.com/) projects. Rather than starting from scratch, this boilerplate is designed to get the ball rolling immediately. Install it, configure it, tweak it, push it.

## Features

- Available as a starter kit or as [Jekyll theme gem](http://jekyllrb.com/docs/themes/)
- Simple and elegant design that can be used out of the box or as solid starting point
- Tested in all major browsers, including IE and Edge
- Configurable colours and typography in a single settings file
- Extensive set of shortcodes to include various elements; such as buttons, icons, figure images and more
- Solid typographic framework from [Sassline](https://sassline.com/)
- Configurable navigation via a single file
- Modular Jekyll components
- Post category support in the form of a single post index page grouped by category
- Built in live search using JavaScript
- Contact form built in using [Formspree](https://formspree.io/)
- Works on [GitHub Pages](https://pages.github.com/) out of the box
- Designed with [Siteleaf](http://www.siteleaf.com/) in mind
- Has 9 of the most popular networks as performant sharing buttons
- Has documentation

## Examples

Here are a few examples of Alembic out in the wild being used in a variety of ways:

- [bitpodcast.com](https://bitpodcast.com/)
- [joelcagedesign.com](https://joelcagedesign.com/)
- [bawejakunal.github.io](https://bawejakunal.github.io/)
- [case2111.github.io](http://case2111.github.io/)
- [www.10people.co.uk](http://www.10people.co.uk/)
- [hrkeni.me](http://hrkeni.me/)
- [venuthatikonda.github.io](https://venuthatikonda.github.io/)
- [ccs17.bsc.es](https://ccs17.bsc.es/)

## Installation

### As a Boilerplate / Fork

1. [Fork the repo](https://github.com/daviddarnes/alembic#fork-destination-box)
2. Clone down the repo with `$ git clone git@github.com:username/reponame.git`
3. Delete the following unnecessary files/folders: `demo/`, `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, `LICENSE`, `screenshot.png` and `alembic-jekyll-theme.gemspec`
4. Change the `logo.svg` and `default-social-image.png` in the `assets/` folder to your own branding
5. Configure your site settings using the `_config.yml`, more info can be found in [Configuration](#configuration)
5. Change the `CNAME` record to your projects' record
6. Install bundler with `$ gem install bundler`
7. Install gems with `$ bundle install`
8. Run Jekyll with `$ bundle exec jekyll serve --watch`
9. Begin hacking for your project

### As a Jekyll 3.3 theme gem

1. Download the starter `/demo` content, [quick download link](https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/daviddarnes/alembic/tree/master/demo)
2. Configure your site settings using the `_config.yml`, more info can be found in [Configuration](#configuration)
3. Create a `logo.svg` and `default-social-image.png` in a new `assets/` folder
4. Install bundler with `$ gem install bundler`
5. Install gems with `$ bundle install`
6. Run Jekyll with `$ bundle exec jekyll serve --watch`
7. Begin hacking for your project

### Boilerplate & Theme differences

The boilerplate kit is better for more drastic hacking and changes, a project that's quite different to any other and needs a lot of custom work done. Additionally you'll only be able to use this method if you want to host it on GitHub Pages, as [themes can't be submitted](https://pages.github.com/themes/)... yet.

Using the theme will allow you to receive updates made and will be more programmatic. To make your own changes you'll need to overwrite the files with your own. For example: If I want to change the colours and typography of my site I'll need to copy the [`_settings.scss`](https://github.com/daviddarnes/alembic/blob/master/_sass/_settings.scss) file and create my own in `_sass/_settings.scss` with my own changes. This is the same for all files within the theme, which means your own project will be more lean than if you were to use the boilerplate.

## Configuration

There's a number of settings you'll need to change before you can start hacking away at files. Here's a run down of what you'll need to change:

### Gem dependency settings
`twitter`, `author` and `social` values will need to be changed to the projects' social information or removed. Look for the `Gem settings` comment within the `/_config.yml` file. These values are for the [jekyll-seo-tag](https://github.com/jekyll/jekyll-seo-tag) - follow the link to find out more.

### Site settings
You'll need to change the `description`, `title` and `url` to match with the project. You'll also need to replace the `/assets/logo.svg` `/assets/default-social-image.png` with the project logo and default social image. The `email` needs to be changed to the email you want to receive contact form enquires with. The `disqus` value should be changed to your project username on [Disqus](https://disqus.com). Look for the `Site settings` comment within the `/_config.yml` file. The `repo` setting is optional, for now, and can be removed entirely, if you wish.

### Site navigation
There are a total of 4 different navigation types:

- `navigation_header`: The links shown in the header (it is also used on the 404 page)
- `navigation_footer`: The links shown in the footer
- `social_links`: The social icon links that are shown in the sidebar
- `sharing_links`: The social sharing buttons that are shown at the bottom of blog posts

All navigations can be edited using the `_config.yml` file. To see example usage either look for the `Site navigation` comment within the `/_config.yml` file or see [the nav-share.html include](#nav-sharehtml).

If there are no items for the `navigation_header` or `navigation_footer`, they will fallback to a list of pages within the site. The `social_navigation` properties should either be one that is already in the list (so `Twitter` or `Facebook`) or simply `link`, this is so an icon can be set for the link.

## Using includes

There are 2 main types of includes: ones designed for the site and ones that are designed as shortcodes. Here are a list of the shortcode includes:

### `button.html`
A button that can link to a page of any kind.

Example usage: `{% include button.html text="I'm a button" link="https://david.darn.es" %}`

Available options:
- `text`: The text of the button _required_
- `link`: The link that the button goes to _required_
- `icon`: The icon that is added to the end of the button text
- `color`: The color of the button

### `figure.html`
An image with optional caption.

Example usage: `{% include figure.html image="/uploads/feature-image.jpg" caption="Check out my photo" %}`

Available options:
- `image`: The image shown _required_
- `caption`: A caption to explain the image
- `position`: The position of the image, `left` or `right`

### `icon.html`
An icon.

Example usage: `{% include icon.html id="twitter" %}`

Available options:
- `id`: The reference for the icon _required_
- `title`: The accessible label for the icon
- `color`: The desired colour of the icon

### `nav-share.html`
A set of buttons that share the current page to various social networks, which is controlled within the `_config.yml` file under the `sharing_links` keyword.

Example usage: `{% include nav-share.html %}`

Available options:
``` yml
Twitter: "#1DA1F2"
facebook: "#3B5998"
Google+: "#DC4E41"
Pinterest: "#BD081C"
LinkedIn: "#0077B5"
tumblr: "#36465D"
Reddit: "#FF4500"
Hacker News: "#ff6600"
Designer News: "#2D72D9"
Email: ""
```

_The first item is the name of the network (must be one of the ones stated above) and the second is the colour of the button. To remove a button just remove the line of the same name._

### `video.html`
A YouTube video.

Example usage: `{% include video.html id="zrkcGL5H3MU" %}`

Available options:
- `id`: The YouTube ID for the video _required_

### `map.html`
A Google map. _See Google [My Maps](https://www.google.com/mymaps)_

Example usage: `{% include map.html id="1UT-2Z-Vg_MG_TrS5X2p8SthsJhc" %}`

Available options:
- `id`: The map ID for the video _required_

### `site-form.html`
Adds a contact form to the page.

Example usage: `{% include site-form.html %}`

This include has no options. Use the `email` option in the `/_config.yml` to change to the desired email.

### `site-search.html`
Adds a search form to the page.

Example usage: `{% include site-search.html %}`

This include has no options. This include will add a block of javascript to the page and javascript reference in order for the search field to work correctly.

## Page layouts

As well as `page`, `post`, `blog`, there are a few alternative layouts that can be used on pages:

- `categories`: Shows all posts grouped by category, with an index of categories in a left hand sidebar
- `search`: Adds a search field to the page as well as a simplified version of the sidebar to allow more focus on the search results

## Page and Post options

There are some more specific options you can apply when creating a page or a post:

- `aside: true`: Adds a sidebar to the page or post, this is false by default and will not appear
- `comments: false`: Turns off comments for that post
- `feature_image: "/uploads/feature-image.jpg"`: Adds a full width feature image at the top of the page
- `feature_text: "Example text"`: Adds text to the top of the page as a full width feature with solid colour; supports markdown. This can be used in conjunction with the `feature_image` option to create a feature image with text over it
- `indexing: false`: Adds a `noindex` meta element to the `<head>` to stop crawler bots from indexing the page, used on the 404 page

> **Note:** The Post List Page options are actually in the collection data within the `_config.yml` file.

## Credits

- Thanks to [Simple Icons](https://simpleicons.org/) for providing the brand icons, by [Dan Leech](https://twitter.com/bathtype)
- Thanks to [Sassline](https://sassline.com/) for the typographic basis, by [Jake Giltsoff](https://twitter.com/jakegiltsoff)
- Thanks to [Flexbox mixin](https://github.com/mastastealth/sass-flex-mixin) by [Brian Franco](https://twitter.com/brianfranco)
- Thanks to [Normalize](https://necolas.github.io/normalize.css/) by [Nicolas Gallagher](https://twitter.com/necolas) and [Jonathan Neal](https://twitter.com/jon_neal).
- Thanks to [pygments-css](http://richleland.github.io/pygments-css/) for the autumn syntax highlighting, by [Rich Leland](https://twitter.com/richleland)
