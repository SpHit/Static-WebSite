+++
title = "Reminders"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
[menu.main]
  weight = 5
  parent = "docs-shortcodes"
+++

Add reminders to your content pages so you don't forget to make that one change again!

The `{{</* remind */>}}` shortcode throws an error while building non-draft (published) pages. This will cause automatic "build and publish" sequences to fail, *which is intended*. The point of the reminder is to get to it before you publish the page!

To avoid interfering with the development process, `{{</* remind */>}}` does *not* throw errors on draft pages. This also means that you do not receive your reminders until you undraft the page.

# Usage

```
{{</* remind */>}}
Update reminder shortcode docs with example of shortcode usage
{{</* /remind */>}}
```
**Output (in terminal, while building):**

```
ERROR 2018/03/10 14:45:51 REMINDER: Update reminder shortcode docs with example of shortcode usage
```