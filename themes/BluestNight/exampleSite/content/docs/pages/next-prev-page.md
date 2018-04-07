+++
title = "Page Navigation"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
enable_toc = true
[menu.main]
  weight = 5
  parent = "docs-pages"
+++

BluestNight supports using the Hugo built-in `NextInSection` and `PrevInSection` [page variables] to provide "next" and "previous" links to the next and previous page in the same [section](https://gohugo.io/content/sections/). On its own, this works great for linking a reader to next oldest or newest post from the one they have just finished reading.

Sometimes you want a specific order to your pages, though, and that's not the one that Hugo gives you. So, BluestNight also gives you the option to specify a custom content file to use as the "next" or "previous" page, as well as the ability to not show one or both buttons, even if there is a valid "next" or "previous" page.

<!--more-->

# Setup

Set `post_navigation` to `true` under `[Params]` in your site's configuration file **OR** a particular page's front matter

```
# In config.toml

[Params]
  post_navigation = true
```

```
+++
# In some-content.md
# Other front-matter goes here

post_navigation = true
+++
```

You can also have navigation enabled sitewide but disable it on a particular page by setting `post_navigation` to `false` in the front matter.

```
+++
# In some-content.md
# Other front-matter goes here
# No next/previous buttons will be generated
post_navigation = false
+++
```

# Custom targets

To set custom targets for a page's next/previous links, set the values of `custom_next` and/or `custom_prev` to the relative path of the page's content file. That is, for a file located under `SITE_ROOT/content/post/my-cool-page.md`, the value should be `post/my-cool-page.md`.

**Make sure there are no leading slashes, or else the button will not be created**

```
+++
# In post/some-content.md
# Other front-matter goes here

custom_next = "post/my-cool-page.md"
custom_prev = "post/my-other-cool-page.md"
+++
```

# Disable a button

For pages that you want to order in any order other than by date, Hugo might say that your first page has a page that comes "previous" and will try to create a previous button on a page where you don't want one. If you set `custom_prev` or `custom_next` to `"none"`, its corresponding button will not be created.

> Actually, any value that is not a valid path to a content file (as described above) will cause the button to not load. It's simpler to tell people to use `"none"`, even though `"nope"`, `"hide"`, and `"disable"` will all work as well.

```
+++
# In post/some-content.md
# Other front-matter goes here

custom_next = "post/my-cool-page.md"
# No "previous" button will be created
custom_prev = "none"
+++
```
