+++
title = "Authorbox"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
enable_toc = true
[menu.main]
  weight = 1
  parent = "docs-pages"
+++

Use the authorbox to provide attribution to the author of a post or page.

The authorbox feature is based on the [`member` shortcode](shortcodes/members) and requires the same [setup](shortcodes/members#setup) in order to work.

**Note:** if the `URL` key is set in the author's data file, the `<a>` tag linking to the URL will have the `rel="author"` attribute set on it.

<!--more-->

# Usage

The author for authorboxes can be set sitewide and/or specific to each page.

To enable authorboxes, set `authorbox` to `true` under `Params` in the site configuration file. An example using TOML:

```
[Params]
    authorbox = true
```

## Set Site Author

To set a default author to be used on a post if authorboxes are enabled and an author isn't set for the page, add a line under `Params` setting `author` to the value under `Name` in the author's data file:


```
[Params]
    authorbox = true
    author = "Michael Bryant"
```

## Set Page Author

Someone other than the default author has authored a post for the site and you'd like to set them as the author of just that one page. You can do so by setting the value of `author` in that page's [front matter](https://gohugo.io/content/front-matter/).

```
+++
title = "Hello, World!"
date = "2016-04-09"
# Joe is the author of this page
author = "Joe Smith"
+++

Lorem ipsum...
```

## Selectively Disable

You can also disable the authorbox for a particular page by setting `hide_authorbox` to `true` in the page's [front matter](https://gohugo.io/content/front-matter/).

```
+++
title = "Hello, World!"
date = "2016-04-09"
# Authorbox will not be shown on this page
hide_authorbox = true
+++

Lorem ipsum...
```
