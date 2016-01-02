# hexo-theme-bootstrap-blog

A simple [Bootstrap] v3 blog theme for [Hexo].

Based on the [official Bootstrap Blog example template](http://getbootstrap.com/examples/blog/).

Demo site: <http://cgmartin.github.io/hexo-theme-bootstrap-blog/>

## Setup Instructions

### Install

**This theme requires Hexo 2.4 and above.**

1) Install theme:

```bash
$ git clone https://github.com/cgmartin/hexo-theme-bootstrap-blog.git themes/bootstrap-blog
```

2) (optional) Install [hexo-tag-bootstrap](https://github.com/wzpan/hexo-tag-bootstrap) for more Bootstrap tags (textcolors, buttons, labels, badges, etc.):

```bash
$ npm install hexo-tag-bootstrap --save
```

### Enable

Modify the `theme` setting in `_config.yml` to `bootstrap-blog`.

### Update

``` bash
cd themes/bootstrap-blog
git pull
```

## Configuration

``` yml
# File: themes/bootstrap-blog/_config.yml

# Header
menu:
  Home: /
  Archives: /archives
rss: /atom.xml

# Content
excerpt_link: Read More
fancybox: true

# Sidebar
sidebar: true
widgets:
- about
- category
- tag
- tagcloud
- archives
- recent_posts

# Miscellaneous
google_analytics:
favicon:
twitter:
google_plus:
```

- **menu** - Navigation menu (map of Titles to URLs)
- **rss** - RSS link (ie. "/atom.xml")
- **excerpt_link** - "Read More" link at the bottom of excerpted articles. `false` to hide the link.
- **fancybox** - Enable [Fancybox] for images
- **widgets** - Enable sidebar widgets ([more info below](#sidebar))
- **google_analytics** - Google Analytics ID
- **favicon** - Favicon path (ie. '/favicon.ico')
- **twitter_id** - Twitter ID of the author (ie. `@c_g_martin`)
- **google_plus** - Google+ profile link

## Features

### Font Awesome

A custom tag for [Font Awesome] icons is available for use.

*Copied from [akarzim/hexo-tag-fontawesome](https://github.com/akarzim/hexo-tag-fontawesome).*

Usage:
```
{% fa [icon-name] [options...] %}
```

Examples:
```
{% fa info-circle %} Info tip
{% fa refresh spin %} Animated loading spinner
{% fa home fw %} Fixed-width icon
```


### Fancybox

This theme uses [Fancybox] to showcase your photos. You can use the image Markdown syntax or fancybox tag plugin to add your photos.

Usage:
```
![img caption](img url)

~or~

{% fancybox img_url [img_thumbnail] [img_caption] %}
```

### Callouts

A custom tag for the [Bootstrap "callout" style](http://cpratt.co/twitter-bootstrap-callout-css-styles/) is available for use.

Usage:
```
{% callout [type:default|primary|success|info|warning|danger] %}
...content...
{% endcallout %}
```

Example:
```
{% callout info %}
#### {% fa info-circle %} Info tip
This is some callout content
{% endcallout %}
```

### Sidebar

This theme provides 6 built-in widgets that can be displayed in the sidebar:

- [about](./layout/_widget/about.ejs) \*
- [category](./layout/_widget/category.ejs)
- [tag](./layout/_widget/tag.ejs)
- [tagcloud](./layout/_widget/tagcloud.ejs)
- [archives](./layout/_widget/archives.ejs)
- [recent_posts](./layout/_widget/recent_posts.ejs)

All widgets are enabled and displayed by default. You can toggle them on/off with the `widgets` setting in the theme's [_config.yml](./config.yml).

\* **NOTE**: The "about" widget contains static Lorem Ipsum text by default. You'll want to edit it for your site or disable the widget in the [theme config](./config.yml). You can also modify it to include contents from a Markdown page:
```html
<div class="sidebar-module sidebar-module-inset">
  <h4>About</h4>
  <%- site.pages['data'].find(function(p) { return p.path === 'about/index.html'; }).content %>
</div>
```
...then run `hexo new page about` to create the Markdown page.


## Development

The [default Landscape Hexo theme](https://github.com/hexojs/hexo-theme-landscape) was used as the starting point and heavily edited for this theme.

The Landscape Stylus styles have been replaced with standard CSS files which override `bootstrap.min.css`. Stylus is used only for [bundling the CSS files](./source/css/styles.styl). Feel free to convert the CSS to your pre-processor of choice (Stylus, LESS, Sass, etc.).

## License

[MIT License](http://cgm.mit-license.org/)

Copyright © 2016 Christopher Martin

[Hexo]: http://zespia.tw/hexo/
[Fancybox]: http://fancyapps.com/fancybox/
[Font Awesome]: http://fontawesome.io/
[Bootstrap]: http://getbootstrap.com/
