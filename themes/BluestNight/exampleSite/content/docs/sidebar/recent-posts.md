+++
title = "Recent Posts"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
[menu.main]
  weight = 4
  parent = "docs-sidebar"
+++

Display your most recent posts in the sidebar!

The recent article sidebar widget displays the ten most recent pages under the `post` [section](http://gohugo.io/content/sections/), as well as buttons to subscribe to the RSS feeds of the whole site and the current section or taxonomy (tag/category).

<!--more-->

{{% alert %}}
Hugo considers a content folder a "section" if it is a direct child of the `content/` folder (e.g. `content/post/`) or if it contains an `_index.md` file. The section that BluestNight matches is the closest valid section to the current page.
{{% /alert %}}

For example, this site has the folder `docs/` as a direct child of the `content/` folder, so it is a section. The child folders `pages/`, `shortcodes`, `sidebar`, and `site` do not have an `_index.md` file, so they are not a nested section. Thus the closest valid section for a page in any of those folders is `docs`.

<!--more-->

# Setup

Set `recent_articles` to `true` under `Params.widgets` in the site configuration file.

```
# config.toml

[Params.widgets]
    recent_articles = true # Enable recent articles view
```
