+++
title = "Bug Fixes & Setup Guides"
date = "2018-03-14T14:57:15-07:00"
hide_authorbox = false
disable_comments = false
categories = ["Announcements"]
tags = ["releases", "bug fixes", "features"]
+++

A lot has gone on since the last update post. New features, a ton of bug fixes, style tweaks, and a new setup guide!

<!--more-->

# Setup Guides

Before going into the changes made to the theme itself, I'd like to announce the existence of the BluestNight [setup guide]({{< ref "setup-guide.md" >}}) and related [site template](https://gitlab.com/BluestNight/site-template).

With so many options built into BluestNight, it can be a little confusing to get a new Hugo site set up with it. The site template comes with a documented `config.toml` file that includes links to relevant pages of documentation on this site. The guide is a little sparse right now, but will get fleshed out as time goes on.

# Important Changes

Here are the things that may break or otherwise change how things were normally set up in BluestNight:

- Alegreya has been added as a more "normal" serif font. Zilla Slab is still available as the "slab-serif" option.
- List markers (bullet points, etc) are now inside the list block, not outside (in the margins)
- Pagination buttons have been moved and restyled.
- Sites without a tagline will have a larger title.
- The `Params.piwik` and background `fit_width` configuration options are being phased out in favor of [`Params.matomo`]({{< ref "docs/site/analytics.md" >}}) and [`fit`]({{< ref "docs/site/appearance.md#custom-background" >}}), respectively. Both `Params.piwik` and `fit_width` still work for now, but will be removed in a later update.

# New Features

- Default CSS code styles - just set `PygmentsUseClasses = true` in your configuration file. The style will change depending on if your background color is detected as light or dark. This can be [overridden]({{< ref "docs/site/appearance.md#syntax-highlighting" >}}).
- Site [thumbnail image]({{< ref "docs/site/appearance.md#header-thumbnail" >}}) - displays to the left of the site title.
- [KaTeX](https://khan.github.io/KaTeX/) is used with the new [math shortcode]({{< ref "docs/shortcodes/math.md" >}}) to render LaTeX-style math.
- New [`remind` shortcode]({{< ref "docs/shortcodes/reminder.md" >}}) to remind you to get things done before you publish.

# Bugfixes

Lots of them. Some to do with making things line up better, some for making sure things are the right colors, some to make sure things don't break. It's best if you just look at the full list of changes below.

# What's Next?

I've fallen behind in keeping up with the new features taking place in Hugo, so that and bug fixing will be my focus for now.

- Related content - Probably a row of 2-4 links just above or below the authorbox (below the page content but above comments).
- Image processing - If `medium_src` and/or `small_src` are not defined in the site configuration, automatically resize the next largest specified image so it is as wide as the largest possible medium/small screen (1024px or 640px, respectively).
- Page Bundles/Resources - Honestly, there is so much here that I'm still not quite sure how this feature works. It looks incredibly powerful and, if used correctly, may lead to an overhaul in some features in BluestNight. Some ideas that *may* find their way into BluestNight are:
  - A shortcode to `include` content from one content file into another
  - A replacement for the built-in `figure` shortcode that includes options for modifying the image (or, you know, you could edit it yourself)
  - Who knows what else?

# All Changes

- [342e5746](https://gitlab.com/BluestNight/BluestNight/commit/342e5746b7a735f256d306f88986bafdb60aa0bc) Fixed button stylings, especially in tables
- [2d993ba0](https://gitlab.com/BluestNight/BluestNight/commit/2d993ba0fee4f142f6092196560dd7ddfbcf5db3) Add default CSS code styles, intelligently chosen based on theme colors
- [d5265a05](https://gitlab.com/BluestNight/BluestNight/commit/d5265a05ee49b37745f9f2eb5df3c3c1f4a4719c) Fix build errors when no site menu is defined
- [3bbe89e4](https://gitlab.com/BluestNight/BluestNight/commit/3bbe89e4f21d4fc2c6b3dd75cfb6963b69d47379) Add site thumbnail/logo
- [fc79c457](https://gitlab.com/BluestNight/BluestNight/commit/fc79c457ed5154801b1326b504e0537858543050) Hide site logo if the screen is too small
- [e295d834](https://gitlab.com/BluestNight/BluestNight/commit/e295d834eb8ed5ddd0719477e90a0b5b73bb8f03) Actually hide hidden things
- [01826a9e](https://gitlab.com/BluestNight/BluestNight/commit/01826a9e4c23e16597201053e22edde1ee80daf6) Remove random space character
- [7812ccf5](https://gitlab.com/BluestNight/BluestNight/commit/7812ccf5063dd20485247056c166e887462b6391) Choose minified or not JavaScript based on a configuration parameter
- [6c52b5f8](https://gitlab.com/BluestNight/BluestNight/commit/6c52b5f84883cd823a69f9768b8b174ed6c01f27) Use cacheable version of the Iubenda JavaScript
- [38845919](https://gitlab.com/BluestNight/BluestNight/commit/38845919ef55a17f408b9d76a5e73a84bbb882e9) Finalize light/dark code style defaults
- [24d215a3](https://gitlab.com/BluestNight/BluestNight/commit/24d215a33b898e47fbaec46b7749fd5245c4f1f9) Hide images from the Android gallery app (for mobile development)
- [1f97d475](https://gitlab.com/BluestNight/BluestNight/commit/1f97d475d3d02ae3ec1909a323b193e9d60cbc34) Separate `#main-nav` styles from widget styles
- [1933e206](https://gitlab.com/BluestNight/BluestNight/commit/1933e206d4f529381835e398f42793dad99944a5) Improve site header appearance and behavior
- [c98af360](https://gitlab.com/BluestNight/BluestNight/commit/c98af36011ffe9944ef5d8ea2b804d688bc02aad) Outside bullets look weird - move them inside where they belong
- [e56f48e7](https://gitlab.com/BluestNight/BluestNight/commit/e56f48e7055ac180b8a26b7cac5f7def9f283a8d) Leave a space between next/prev page title and button icons
- [3bf7a367](https://gitlab.com/BluestNight/BluestNight/commit/3bf7a36726c05a05fa922edb8330dff70cb8874a) Improve pagination styles
- [59ac2d8b](https://gitlab.com/BluestNight/BluestNight/commit/59ac2d8bc19854d40aa29b05fbf09f7a90d645a9) Make a title without a tagline larger
- [0a7aafb6](https://gitlab.com/BluestNight/BluestNight/commit/0a7aafb6b004bc81cafdabc775c29ec2158627a5) Add math parsing support by KaTeX
- [d710afac](https://gitlab.com/BluestNight/BluestNight/commit/d710afacad753e7adedbe042178f8848d8393cf0) Don't let Iubenda block scripts that don't set cookies
- [335a7f35](https://gitlab.com/BluestNight/BluestNight/commit/335a7f358cffe8e9b398c3ee4633b95d3bdedbc0) Fix JSON generation for content containing backslashes
- [b033a63a](https://gitlab.com/BluestNight/BluestNight/commit/b033a63a4114f9bab54bbf49da585ed3ea91f36f) Use author for copyright, if available
- [42c57eac](https://gitlab.com/BluestNight/BluestNight/commit/42c57eac36a14578d5ef17aa40d4e51d42ee7613) Fix issues with sites in subdirectories
- [a59de0fe](https://gitlab.com/BluestNight/BluestNight/commit/a59de0feddad7cbfc9eddcb054d11c9199780ce0) Fix menus for sites in subdirectories
- [16fc7baf](https://gitlab.com/BluestNight/BluestNight/commit/16fc7baf56e29c284e219fce198e2d041883c125) Add reminder shortcode
- [e52819f3](https://gitlab.com/BluestNight/BluestNight/commit/e52819f3151c0f9cf6ab98ef9d86f7a399181b04) Fix bad "Subscribe to ______" link in the sidebar on taxonomy term pages
- [659c1b5a](https://gitlab.com/BluestNight/BluestNight/commit/659c1b5ad707969a09ecae173e6ccb39fc4ab5b4) Remove attempt to fill in the author field on archetype templates, as it caused errors
- [78be93d5](https://gitlab.com/BluestNight/BluestNight/commit/78be93d5d2c69eccadf62b07386b67b450895e1a) Prioritize site Copyright parameter and use .Site.Params.Author for copyright field
- [43942892](https://gitlab.com/BluestNight/BluestNight/commit/4394289247432a1b66deeccea5aff26b688b2191) Add Alegreya as a "normal" serif font
- [37ecd2cc](https://gitlab.com/BluestNight/BluestNight/commit/37ecd2cc57d7cbc78c3705e3e726421e578933b1) Add the `fit` background configuration option to replace `fit_width`
-[71f62a95](https://gitlab.com/BluestNight/BluestNight/commit/71f62a958479e050c077c44cd1cddbec09dc722d) Rename Piwik stuff to Matomo
-[221e1094](https://gitlab.com/BluestNight/BluestNight/commit/221e109449bf377e94a10e48af0c9e7c8a13865d) Fix CSS errors in code styles, added minified versions
-[48ad7e01](https://gitlab.com/BluestNight/BluestNight/commit/48ad7e01020817d4939af13e7b0d2efd6b0271ea) Updated README
-[ddd82dc2](https://gitlab.com/BluestNight/BluestNight/commit/ddd82dc278ca295171f8a092c774242dec901448) Make sure code inside strikethroughs are struck through
-[18eb10ac](https://gitlab.com/BluestNight/BluestNight/commit/18eb10ac16070fbe4406cfe98b2023a72ae39118) Fix an issue where the site thumbnail was visible when it didn't fit next to the title