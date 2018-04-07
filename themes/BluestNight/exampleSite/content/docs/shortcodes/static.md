+++
title = "Link To Static Files"
hide_authorbox = true
description = "There's a limitation with the way links are created in markdown. Sites whose BaseURL is in a subdirectory of a site (i.e. https://example.com/subdir/) may not link correctly using existing methods. This shortcode helps circumvent this limitation."
disable_comments = true
categories = ["Documentation"]
[menu.main]
  weight = 7
  parent = "docs-shortcodes"
+++

(Examples use a file at `/static/path/to/image.jpg`)

There's a limitation with the way links are created in markdown. In order to link to static files in content files, we need to either:

1. Write a path relative to the current directory, with `../` and the like, so a file at `content/section/subsection/page.md` would need `../../../path/to/image.jpg`

1. Prefix the path with a leading `/`, which causes the path to resolve to `example.com/path/to/image.jpg`

The first is a pain to have to do, and the second only works if the `baseURL` of your Hugo site is `example.com`. A site at `example.com/subdir/` will still resolve the link to `example.com/path/to/image.jpg`, which won't exist.

To get around this limitation (at least until it gets [implemented in Hugo](https://github.com/gohugoio/hugo/issues/3732)), BluestNight includes a shortcode called `static` that will correctly resolve links to static files according to the site's `baseURL`. The syntax is similar to the [`ref` and `relref`](https://gohugo.io/content-management/shortcodes/#ref-and-relref) shortcodes:

```
![Image alt text]({{</* static "path/under/static/folder/file.jpg" */>}})
[Link text]({{</* static "other/static/folder/file.txt" */>}})
```

Example output, using a `baseURL` of `http://example.com/subdir/`:

```html
<img src="http://example.com/subdir/path/under/static/folder/file.jpg" alt="Image alt text" />
<a href="http://example.com/subdir/other/static/folder/file.txt">Link text</a>
```
