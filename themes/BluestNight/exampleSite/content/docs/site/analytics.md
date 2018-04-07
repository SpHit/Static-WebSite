+++
title = "Analytics"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
[menu.main]
  weight = 2
  parent = "docs-site"
+++

BluestNight comes with support for [Matomo](https://matomo.org/) as an site analytics provider. This requires having a Matomo instance hosted somewhere, either [self-hosted](https://matomo.org/download/) or [hosted by Innocraft](https://www.innocraft.cloud/). The theme uses the [JavaScript tracking client](https://developer.matomo.org/guides/tracking-javascript-guide).

<!--more-->

# Setup

Set `enable` to `true` and `host` to the root URL of the Matomo installation under `[Params.matomo]` in your site's configuration file. If your  installation tracks multiple websites, add the site ID number in `site_id`.

```
# In config.toml
[Params.matomo]
    enable = true
    # URL to the root of the matomo installation.
    # Can include paths after the TLD (e.g https://example.com/matomo/)
    host = "https://matomo.example.com"
    # ID number of this site. Defaults to 1 if not included
    site_id = 2
    # Include <noscript> tags to track users with javascript disabled
    track_nojs = true
    # Include a link in the site footer to allow users to opt out of analytics
    enable_optout = true
```

# Ajax "one-click" opt-out

Matomo currently only provides an `<iframe>` as a method of opting out of being tracked. It sucks, looks bad on a themed page, and just generally isn't a great idea. A user thought so too and [created a plugin](https://plugins.matomo.org/AjaxOptOut) that allows developers to create an opt-out *button*. \*GASP!\*

I recommend you install the above plugin and enable support for one-click opting out with the below configuration:

```
# In config.toml
[Params.matomo]
    enable = true
    # URL to the root of the matomo installation.
    # Can include paths after the TLD (e.g https://example.com/matomo/)
    host = "https://matomo.example.com"
    # Include <noscript> tags to track users with javascript disabled
    track_nojs = true
    # Include a link in the site footer to allow users to opt out of analytics
    enable_optout = true
    # Enable ajax "one-click"
    enable_ajax = true
```

**Note:** You will need to [enable cross-domain requests](https://matomo.org/faq/how-to/faq_18694/) in your Matomo installation and set the `Access-Control-Allow-Credentials` header to `true` on the server hosting Matomo.

Nginx: In the Matomo `server {}` block, add the line `add_header Access-Control-Allow-Credentials "true" always;`

Apache (including `.htaccess` files):
Add the following to your server's `<VirtualHost>` block or to a `.htaccess` file at the root of your Matomo installation.
```
<IfModule mod_headers.c>
    SetEnvIf Origin (.*) AccessControlAllowOrigin=$1
    Header add Access-Control-Allow-Origin %{AccessControlAllowOrigin}e env=AccessControlAllowOrigin
    Header set Access-Control-Allow-Credentials true
</IfModule>
```
