+++
title = "Alert"
hide_authorbox = true
disable_comments = true
enable_toc = true
categories = ["Documentation"]
alert = "This is an example of a page-specific alert box. Important information, perhaps about how an article was updated or how the content is not suitable for young readers, should go here. It *can* contain **Markdown**."
[menu.main]
  weight = 1
  parent = "docs-site"
+++

Use an `alert` if you need to make sure that your reader's eye is brought to some important information before they get to the main content. You can have site-wide and page-specific alerts, which work the same except for where they are set.

<!--more-->

Limitations:
- Alerts cannot be dismissed by the reader
- Alerts do not support shortcodes, since they are set in the site config and/or page front matter.

# Site-Wide Alerts

Site-wide alerts appear above both the main content and the sidebar on every page. Use these for important announcements that readers need to see no matter where on the site they are. Long announcements should go into their own blog post, with a link included in the alert.

To set a site-wide alert, set the value of `alert` under `Params` in the `config` file to the content of the alert.

```
[Params]
  alert = "This is my site-wide \"alert\" content *with* Markdown."
```

# Page-Specific Alerts

Page-specific alerts appear above the content of a page but below the page title and metadata (publish date, etc). Use these to indicate important information about the page, perhaps about how an article was updated or how the content is not suitable for young readers.

To set a page-specific alert, set the value of `alert` in the page's front matter to the content of the alert.

```
+++
title = "Example Page"
alert = "This is my page-specific \"alert\" content *with* Markdown."
+++
```

# Shortcode

There is also an alert shortcode for when you want to have an alert box in the middle of your content.

```
Normal content...

{{%/* alert */%}}
The content of the alert box goes here.
{{%/* /alert */%}}

More normal content...
```
