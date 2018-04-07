+++
title = "Customize List Pages"
hide_authorbox = true
disable_comments = true
enable_toc = true
categories = ["Documentation"]
[menu.main]
  weight = 3
  parent = "docs-pages"
+++

BluestNight provides a number of ways for you to customize [list pages](https://gohugo.io/templates/list/) using [`_index.md`](https://gohugo.io/content/using-index-md/) files.

<!--more-->

# Custom content

If you create an `_index.md` file for a list page and put content in it, that content will appear above the list on the generated page.

# Hide the list

Maybe you don't want to display the list of pages, just your custom content. Set `hide_list` to `true` in the front matter of the `_index.md` file and BluestNight will only generate the custom content on that page.

# Show nested sections

**Sections only**

If you want to display the nested sections under the one a list page represents, set `list_subsections` to `true` in the page's front matter. The list will not be displayed if `hide_list` is set to `true`.

# Sort/filter listed pages

By default, BluestNight (and Hugo) sort the pages under a section or taxonomy by date, with the newest page first. You have the ability to choose what page field to sort by and in ascending or descending order. You also have the ability to filter only pages with the file name `index.md`.

## Custom sort field

To sort the entries in the list, set the values of `sort_field` and (optionally) `sort_order` in the list page's front matter. Valid values for `sort_field` are any [ordering page variable](https://gohugo.io/templates/lists/#order-content) without the leading `By` **OR** any front matter variable with the prefix `Params`.

- If the template sorting method you want to use in the Hugo docs is `ByDate`, `sort_field` should be `"Date"`.
- If sorting by the custom front matter parameter `sorting_weight`, `sort_field` should be `"Params.sorting_weight"` (note the lack of a leading `.` on `Params`).

## Custom sort order

Valid values for `sort_order` are `"asc"` and `"desc"`. If `sort_order` is not specified, the order will depend on what makes the most sense for that field. `sort_order` is ignored if `sort_field` is not specified.

- `Date` fields are descending (new first) by default.
- `Title` and `Weight` fields are ascending (A-Z and 1-9) by default.
- Sort fields beginning with `Params` are also ascending by default and **cannot currently be changed**.

To sort the pages in a custom order, you can set a variable in the front matter, for example `sort_weight`, and number the pages in the order you want them to appear in.

```
+++
# file name: _index.md
title = "List page"
sort_field = "Params.sort_weight"
+++

+++
# file name: first.md
title = "First article"
sort_weight = 1
+++

+++
# file name: second.md
title = "Second article"
sort_weight = 2
+++
```

## Filter only index.md

To display only those pages with the file name `index.md`, set `index_only` to `true` in the list page's front matter. You may want to use this if a section contains folders of content that are *not* subsections of this one (i.e. have a file `_index.md`), but only want to list the entry pages of those folders.

```
+++
index_only = true
+++
```

# Examples

This site author wants to display a message to their readers before showing the most recent posts.

```
+++
# Found under "post/_index.md"
title = "My Awesome Posts"
hide_list = false
+++

Before you get to my posts, I just want you all to know how much I appreciate your readership and your feedback on my posts.
```

This site author provides a multi-page how-to guide and wants users to start with a link to the first item so they don't skip ahead.

```
+++
# Found under "how-to/install-linux/_index.md"
title = "How to Install Linux"
hide_list = true # Won't show any other pages under "how-to/install-linux"
+++

If you've ever wanted to install a Linux distribution on your computer but weren't sure how, this guide is for you!

(More introductory stuff about installing Linux - this is a code example, I don't need to write a full paragraph!)

[Start here]({{</* ref "how-to/install-linux/1.md" */>}}).
```
