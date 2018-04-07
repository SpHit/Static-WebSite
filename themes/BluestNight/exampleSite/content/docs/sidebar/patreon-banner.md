+++
title = "Patreon Banner"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
[menu.main]
  weight = 3
  parent = "docs-sidebar"
+++

Have a Patreon account? Add a Patreon banner to the sidebar of your site that links to it!

<!--more-->

# Setup

Add a key `patreon` under `Params.widgets` in your site config file with the value of the "slug" of your Patreon page (the part coming after `patreon.com/`

```
# config.toml
[Params.widgets]
    patreon = "shadow53" # Links to https://patreon.com/shadow53
```

BluestNight will do its best to determine if it should say "Support Me on Patreon" or "Support *Us* on Patreon" by checking how many [members]({{< ref "docs/shortcodes/members.md" >}}) are listed on the site. If one or none, it assumes this is a personal website and will use "Me". If more than one, it assumes the website belongs to an organization and says "Us".

# Custom Banner

BluestNight tries to automatically figure out if the [black]({{< static "images/patreon/patreon_black.svg" >}}) or [white]({{< static "images/patreon/patreon_white.svg" >}}) Patreon banner will fit best on your site by calculating the [relative luminance](https://en.wikipedia.org/wiki/Relative_luminance) of the main backaground color. If this does not work well with your color scheme, or you prefer something other than the default banner, you can specify the URL to a different image. Consider using one of the other official Patreon banners, found [here](https://www.patreon.com/brand/downloads).

When you have the URL to your patreon banner of choice (this can be a relative URL to an image in your `static/` directory), add it under `Params.widgets` as the value for `patreon_banner`.

```
# config.toml
[Params.widgets]
    patreon = "shadow53" # Links to https://patreon.com/shadow53
    patreon_banner = "https://c4.patreon.com/toolbox/patreon_logo.png"
```

The image will be automatically resized on the page to fit within the width of the sidebar.
