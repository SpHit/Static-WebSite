+++
title = "Tag List"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
[menu.main]
  weight = 6
  parent = "docs-sidebar"
+++

Show a cloud of the tags you've used on the site in your sidebar.

This widget currently shows all of the tags used on the website, in order of how often they are used (most common listed first, etc.) You can optionally enable showing how many times the tag has been used.

<!--more-->

# Setup

Set `tags` to `true` under `Params.widgets` in your site's configuration file to enable tags in the sidebar. Set `tags_counter` to `true` to should a count of how often the tag appears on the site in the tag button.

```
# In config.toml

[Params.widgets]
    tags = true # Enable tags in the sidebar
    tags_counter = true # Show how often tags appear
```
