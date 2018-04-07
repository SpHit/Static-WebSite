+++
title = "Summaries"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
enable_toc = true
[menu.main]
  weight = 7
  parent = "docs-pages"
+++

Hugo [provides a mechanism](https://gohugo.io/content/summaries/) for extracting the first part of a page's content to serve as a "summary" of the content. This works if the first bit of content serves as a good summary of the rest of the page. Sometimes, though, it doesn't. There's no built-in method for providing your own text as a "summary" - but there is in BluestNight.

<!--more-->

# Setup

In your page's [front matter](https://gohugo.io/content/front-matter/), provide the text as the value of the `description` parameter. For example:

```
+++
title = "Some Random Page"
description = "A page containing dummy Lorem Ipsum text to illustrate how one can provide a custom page \"summary\" that is not taken from the first bit of text found on the page."
+++

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Ut sodales justo a nibh suscipit, sed condimentum mauris viverra. Morbi felis nisl, tempus ac leo auctor, lobortis ultricies tellus. Mauris iaculis metus at quam vestibulum, nec hendrerit neque consequat. Etiam in auctor risus. Morbi dolor diam, cursus ac tristique vel, rutrum sit amet neque. Praesent vel neque in ex varius ullamcorper. Vivamus eu gravida neque. Pellentesque nec scelerisque nulla.
```

(The backslashes are there to "escape" the double-quotation marks so they aren't interpreted as the end of the description)

# Priority

The order of priority for which kind of "summary" is used is as follows:

1. `description` from the page front matter
1. The Hugo-provided page summary

If, for some reason, BluestNight does not receive text from any of the above (both ended up being empty strings), it will fall back to using the site's generic description for the page. This should not happen unless the site author or theme developer has messed things up.

# Where it's used

The page's summary is used in the following areas:

- When the page appears in a list of pages:
  - The "posts" page
  - A list of pages with a specific tag
  - Etc.
- As the page's description/excerpt for search engine results
