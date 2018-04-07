+++
title = "Appearance"
hide_authorbox = true
disable_comments = true
enable_toc = true
description = "Customize the appearance of your Hugo site by adding a custom background image, changing the colors used for the site, or modifying the default choice of whether to use serif or sans-serif fonts."
categories = ["Documentation"]
[menu.main]
  weight = 3
  parent = "docs-site"
+++

# Custom Background

Add the following to your site's `config.toml` file:

```
[Params.background]
    src = "images/background_lg.png"
    #medium_src = "images/background_med.png"
    #small_src = "images/background_sm.png"
    fit = "auto"
    tile = false
```

- Change `src` to the relative path from the site's baseURL where the background image can be found. In the above example, the file would be found at `{site root}/static/images/background.png`.
- Optionally set `medium_src` and `small_src` to smaller images to use on screens that are at most 1024px and 640px, respectively. If either of these are omitted, the next largest image source will be used.
- Set `fit` to `"contain"` if you want the behavior of CSS [`background-size: contain`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-size?v=example#contain), and `"cover"` if you want the behavior of [`background-size: cover`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-size?v=example#cover), and anything else to not stretch the image at all.

# Custom Colors

Add the following to your site's `config.toml` file:

```
[Params.color]
    page_background = "#000000"
    main_background = "#050505"
    alt_background = "#252525"
    main_text = "#e2e2e2"
    alt_text = "#e2e2e2"
    accent = "#2c8cef"
    accent_text = "#e2e2e2"
```

**The above values represent the default colors in the theme.** Modify them as you'd like.

- `page_background` is the background color for what is "behind" the page. This is the same area as where the background image is applied, so it is a good idea to pick a color that matches the image if you use `fit_width = true` on the background image.
- `main_background` is the background color for most of the content page.
- `alt_background` is the alternate background color for the page. This background is applied to the navigation bar, footer, various buttons, and as the alternate color for zebra-striped tables.
- `main_text` is the font color that corresponds with `main_background`.
- `alt_text` is the font color that corresponds with `alt_background`.
- `accent` is the color applied to the site header, links, and buttons that are hovered over or marked active.
- `accent_text` is the font color that is used when `accent` is being used as the background color.

# Syntax Highlighting

If `PygmentsUseClasses` is set to `true` in the site's configuration file, BluestNight will detect how dark the `alt_background` color (see above) is and apply a default syntax theme as necessary.

If you want to override these defaults, you have two options:

1. Disable `PygmentsUseClasses` by commenting it out or setting it to `false` and set `PygmentsStyle` to the theme you want to use ([Hugo documentation](https://gohugo.io/content-management/syntax-highlighting/#configure-syntax-hightlighter))

2. Create the files `dark.css` and `dark.min.css` (for dark backgrounds) and `light.css` `light.min.css` (for light backgrounds) under `static/css/` in your site's root directory by following the instructions [here](https://gohugo.io/content-management/syntax-highlighting/#generate-syntax-highlighter-css)

# Header Thumbnail

Add a thumbnail - like a personal photo or company logo - to the site header by setting `Params.thumbnail` to the path to the thumbnail image in your site's configuration file. Give it a rounded edge by setting `Params.thumbnail_radius` to a [valid](https://developer.mozilla.org/en-US/docs/Web/CSS/border-radius) CSS `border-radius` value. Images are scaled down to a maximum height of 128 pixels, approximately the height of the header with a site title and tagline.

```
# In config.toml
[Params]
  thumbnail = "path/to/thumbnail.png"
  thumbnail_radius = "10%"
```

# Font Customization

BluestNight uses the following font families:

- [Clear Sans](https://01.org/clear-sans) (sans-serif)
- [Alegreya](https://www.huertatipografica.com/en/fonts/alegreya-ht-pro) (serif)
- [Zilla Slab](https://blog.mozilla.org/opendesign/zilla-slab-common-language-shared-font/) (slab-serif)
- [Source Code Pro](http://adobe-fonts.github.io/source-code-pro/) (monospace)

By default, Clear Sans is used for all text on the on the web page except for `<code>` and `<pre>` blocks, which use Source Code Pro, and any text inside of the [custom font shortcodes]({{< ref "docs/shortcodes/custom-fonts.md" >}}). Alegreya is used by default for text when a page is printed. Zilla Slab used to be the only serif font offered and is still provided for those who prefer it to Alegreya.

These defaults can be modified, though, through the use of four configuration properties and two shortcodes.

## Change Default Font Families

```
[Params.fonts]
  header_style = "sans-serif"
  body_style = "sans-serif"
  print_header_style = "slab-serif"
  print_body_style = "serif"
```

The above code block shows the default values of each of the four configuration properties and how they would appear inside on a configuration file written in TOML. Properties prefixed with `print_` affect printed pages only, while those without affect only the page on a screen. The `header_style` properties set the font family for all page headers, while the `body_style` ones affect the main text of the page (inside the `<article>` tag, for the web developers).

{{% alert %}}
If `header_style` and `body_style` (or `print_header_style` and `print_body_style`) match, the choice of "serif" or "sans-serif" is applied to the *entire* page. If they do not match, text in the footer and sidebar is ignored, unless it is a header.
{{% /alert %}}

## Enabling All Weights

To save on bandwidth, BluestNight includes CSS declarations for only `regular`, `bold`, `italic`, and `bolditalic` variations of the included fonts. The fonts themselves may come with further weights, such as `light`, `medium`, `semibold`, and `black`. Since these extra weights aren't used when styling using markdown, they have been disabled. To reenable them, set `Params.extra_font_weights` to `true` in your site configuration file.

{{% alert %}}
Only enable the extra font weights if you plan on explicitly using them! The font files themselves should not be downloaded either way, but enabling unused fonts increases the length of the CSS stylesheet.
{{% /alert %}}

## Shortcodes
If you want to change the font family for a block of text on a page, you can use the `{{%/* serif */%}}`, `{{%/* slab-serif */%}}`, and `{{%/* sans-serif */%}}` shortcodes.

### Examples

```
{{%/* serif */%}}
This text will **always** be *serif*.
{{%/* /serif */%}}
```

{{< alert >}}
{{% serif %}}
This text will **always** be *serif*.
{{% /serif %}}
{{< /alert >}}

```
{{%/* slab-serif */%}}
This text will **always** be *slab-serif*.
{{%/* /slab-serif */%}}
```

{{< alert >}}
{{% slab-serif %}}
This text will **always** be *slab-serif*.
{{% /slab-serif %}}
{{< /alert >}}


```
{{%/* sans-serif */%}}
This text will **always** be *sans-serif*.
{{%/* /sans-serif */%}}
```

{{< alert >}}
{{% sans-serif %}}
This text will **always** be *sans-serif*.
{{% /sans-serif %}}
{{< /alert >}}

# Favicons

{{% alert %}}
BluestNight recommends using [RealFaviconGenerator](https://realfavicongenerator.net/) to generate your favicons for your site.
{{% /alert %}}

Different web browsers on different systems each expect a different kind of favicon image for *their* platform. BluestNight supports using these different favicons and will automatically include them in the metadata for your website, if found.

BluestNight looks for the following files in the `static` directory:

- `favicon.ico` - the generic favicon. BluestNight adds the query string `?nocache` to the end of the URL so updates to the icon get propagated to users.
- `favicon-DDxDD.png` - favicons of various sizes, where `DDxDD` is their dimensions (e.g. `96x96`).
- `apple-touch-icon.png` - Apple's iOS favicon for adding to the home screen.
- `site.webmanifest` - A JSON [manifest file](https://developer.chrome.com/multidevice/android/installtohomescreen) for Android users to add your site to their homescreen
- `safari-pinned-tab.svg` - An icon for Mac OS X users to pin your site to their start bar.

Also: [Windows Live Tiles](https://docs.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/samples/dn455115(v%3dvs.85))

The website [RealFaviconGenerator](https://realfavicongenerator.net/) allows you to upload a single image and generate all of the above files. Just unzip the contents of the downloaded zip file to the `/static/` folder of your site.

# Footer Attribution

By default, BluestNight displays a small attribution line in the footer with links to [Hugo](https://gohugo.io/) and this website. To disable this, set `Params.hide_attribution` to `true` in your site's configuration file.