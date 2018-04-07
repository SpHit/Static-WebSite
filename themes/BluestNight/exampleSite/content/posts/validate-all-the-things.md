+++
title = "Validate All The Things!"
date = "2017-11-13T18:18:15-07:00"
hide_authorbox = false
disable_comments = false
categories = ["Announcements"]
tags = ["releases", "bug fixes", "features"]
+++

Last month, the Hugo developers released version [0.30](https://github.com/gohugoio/hugo/releases/tag/v0.30) of Hugo. The big-ticket items mentioned in the release notes were the new fast render mode, improvements to template metrics, and improvements to the built-in syntax highlighting.

Another feature added, that was left underneath the release announcement, was the addition of the [`errorf`](https://gohugo.io/functions/errorf/) template function. It seems like a small thing, but has huge implications: it means that theme developers can now safely tell users that they've misconfigured their theme!

<!-- more -->

This is the bulk of the work I've put into BluestNight over the past weeks. Every theme file was carefully looked over for places where user configuration is used and where those configuration options can be validated.

# Example: Validating Colors

For instance, if you are using a [custom color scheme]({{< ref "docs/site/appearance.md#custom-colors" >}}), each of the following is a valid CSS color:

- `#babb1e` (Hexadecimal)
- `#112233FF` (Hexadecimal with alpha)
- `rgb(233, 45, 79)` (RGB color)
- `rgba(233, 45, 79, 0.4)` (RGBA color)
- `rgba(50%, 33%, 12%, 95%)` (RGBA color, using percent values)
- `blanchedalmond` (CSS color keyword, equal to `rgb(255, 235, 205)`)

If you use any of these formats to specify a CSS color, BluestNight is able to validate that it is written correctly and give you an error if something is wrong:

- `#1122334` (Missing a second digit for the alpha value)
- `rgb(256, 123, 24)` (The `r` value is greater than `255`)
- `rgba(255, 123, 24, 1.1)` (The alpha value is greater than `1`)

# Other Examples

One of the other big areas that I wanted to improve on was in the area of options that required other options to be set a certain way. For instance, in order to use site search, the option `Params.widgets.search` needs to be set to `true`, but you also need to add `"JSON"` as an output format for the home page in order to generate the search index file.

Previously, you could set `Params.widgets.search` to `true` and have the search bar enabled but not work because the index was never created. Now, Hugo will warn you to enable the JSON output format too. This change also effects any other option that requires other options to be set a certain way in order to work.

# Social Icons in Member Boxes

One feature that was added during this process is the ability to add [social icons]({{< ref "docs/shortcodes/members.md#social-links" >}}) for a particular site member, which will appear on their member/authorboxes. The syntax is the same as the site's social icons. For example, my data file on this site currently looks like this:

```yaml
Name     : Michael Bryant
Img      : images/avatar.jpg
Position : "Creator"
Url      : "https://shadow53.com/"
Bio      : |
   A college student at Seattle Pacific University.
   Programmer and blogger on the side. Author of BluestNight.
social   :
   linkedin: "shadow53"
   gitlab: "Shadow53"
   github: "Shadow53"
```

You can see the result of adding the social icons in the authorbox at the end of this post.

# Miscellaneous Changes

- [[2dd4d73a]](https://gitlab.com/BluestNight/BluestNight/commit/2dd4d73a73384994fe53dcff7457dac904630330) Remove unused template files
- [[eaa1cb96]](https://gitlab.com/BluestNight/BluestNight/commit/eaa1cb96bf3bb942642b3bc57629743a92e217f3) Remove float partial in favor of `float` template function
- [[f93302d1]](https://gitlab.com/BluestNight/BluestNight/commit/f93302d11e4c4eebf413e543bb2d1e235461247f) Fixed an accidental hardcoding of a value
- [[e003dfe3]](https://gitlab.com/BluestNight/BluestNight/commit/e003dfe31d1e0d6cae2a972ae66c9ec2e0b78842) Check if a value is inside a slice of allowed values instead of using nested `or` statements
- Various other changes relating to cleaning up the codebase.
