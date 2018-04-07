+++
title = "Members"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
[menu.main]
  weight = 3
  parent = "docs-shortcodes"
+++

Looking to put together a nice Members page for your site, but don't want to write a bunch of custom HTML to make it look good?

Just use the `{{</* member */>}}` shortcode!

<!--more-->

# Setup

**This setup is necessary for both the `member` shortcode *and* the `authorbox` feature!**

Create a data file for each member in your site's `data/members` directory with keys `Name`, `Img` (optional), `URL` (optional), `Position`, and `Bio`.

The `URL` field should indicate that particular member's home page, either on the same site (if they have a profile page) or on a separate site.

If a user doesn't have an `Img` key, the [default photo](https://gitlab.com/BluestNight/BluestNight/blob/master/static/images/profile.jpg) will be used instead.

An example data file, to be found under `data/members/shadow53.yml`:

## Social Links

Member data files support [social icons]({{< ref "docs/site/social-icons.md" >}}) to link to that member's social accounts/pages. The syntax is the same as for the site itself - see the example below for more. Note that `social` is all lowercase.

## Example

```yaml
# This example uses YAML
Name     : "Michael Bryant"
Img      : "/path/to/picture/of/michael.jpg"
Position : "Awesome Theme Designer"
URL      : https://mnbryant.com
Bio      : |
  I'm Michael, also known as Shadow53. This bio section
  is intended to have a small paragraph's worth of text
  in it so it takes up about as much space on the screen
  as the profile picture, because I think that looks nice.
  Lorem Ipsum. Foo, bar, baz, and all that.
social   :
   linkedin: "shadow53"
   gitlab: "Shadow53"
   github: "Shadow53"
```

# Usage

Just use the shortcode wherever you want the member entry to appear on the page. There are two syntaxes for the code, a shorthand for the default options and a longer version with more configurability.

The short syntax is `{{</* member "Member Name" */>}}` where `"Member Name"` is replaced with the value of the `Name` field in the data file. So, using the example above:

```
{{</* member "Michael Bryant" */>}}
```

{{< member "Michael Bryant" >}}

The longer syntax is `{{</* member name="Member Name" noborder="false" */>}}`. This example will look exactly the same as the shorthand version above, but changing `noborder` to `true` will remove the top and bottom borders from the memberbox.

```
{{</* member name="Michael Bryant" noborder="true" */>}}
```

{{< member name="Michael Bryant" noborder="true" >}}
