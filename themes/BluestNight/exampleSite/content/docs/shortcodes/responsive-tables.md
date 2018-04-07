+++
title = "Responsive Tables"
hide_authorbox = true
disable_comments = true
enable_toc = true
categories = ["Documentation"]
alert = "Make sure to read the [known limitations](#known-limitations) section below."
[menu.main]
  weight = 6
  parent = "docs-shortcodes"
+++

The markdown processor bundled with Hugo has the ability to parse [markdown tables](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#tables), but these tables are not mobile-friendly (like most tables).

This didn't work well for me, since my markdown tables were rendering poorly on mobile devices due to automatic content sizing. More often than not, the table ended up overflowing and looking unprofessional. So I put together a set of shortcodes to help create tables that would shift around on small screens to be more readable.

Below you can compare a normal markdown table with a responsive table. Just resize the window or, if you're on mobile, try rotating your screen between portrait and landscape.

**Normal table**

|     Column 1     |    Column 2    |     Column 3     |     Column 4      |
|------------------|----------------|------------------|-------------------|
| Some random text | Blah blah blah | Random data here | The fourth column |
| Another row      | Hey, why not?  | Zebra stripes!   | End of the line   |

```md
|     Column 1     |    Column 2    |     Column 3     |     Column 4      |
|------------------|----------------|------------------|-------------------|
| Some random text | Blah blah blah | Random data here | The fourth column |
| Another row      | Hey, why not?  | Zebra stripes!   | End of the line   |
```

**Responsive table**

{{< table "Column 1" "Column 2" "Column 3" "Column 4" >}}
  {{< table-row >}}
    {{% table-cell %}}Some random text{{% /table-cell %}}
    {{% table-cell %}}Blah blah blah{{% /table-cell %}}
    {{% table-cell %}}Random data here{{% /table-cell %}}
    {{% table-cell %}}The fourth column{{% /table-cell %}}
  {{< /table-row >}}
  {{< table-row >}}
    {{% table-cell %}}Another row{{% /table-cell %}}
    {{% table-cell %}}Hey, why not?{{% /table-cell %}}
    {{% table-cell %}}Zebra stripes!{{% /table-cell %}}
    {{% table-cell %}}End of the line{{% /table-cell %}}
  {{< /table-row >}}
{{< /table >}}

```
{{</* table "Column 1" "Column 2" "Column 3" "Column 4" */>}}
  {{</* table-row */>}}
    {{%/* table-cell */%}}Some random text{{%/* /table-cell */%}}
    {{%/* table-cell */%}}Blah blah blah{{%/* /table-cell */%}}
    {{%/* table-cell */%}}Random data here{{%/* /table-cell */%}}
    {{%/* table-cell */%}}The fourth column{{%/* /table-cell */%}}
  {{</* /table-row */>}}
  {{</* table-row */>}}
    {{%/* table-cell */%}}Another row{{%/* /table-cell */%}}
    {{%/* table-cell */%}}Hey, why not?{{/*% /table-cell */%}}
    {{%/* table-cell */%}}Zebra stripes!{{%/* /table-cell */%}}
    {{%/* table-cell */%}}End of the line{{%/* /table-cell */%}}
  {{</* /table-row */>}}
{{</* /table */>}}
```

# How To Use

The responsive table is made up of three shortcodes.

1. `{{</* table */>}}`, serves as a container for the other shortcodes and defines the names of each of the columns. After "table" comes a list of column names in the order that they should appear, from left to right.

1. `{{</* table-row */>}}` serves as a container for `{{%/* table-row */%}}` and does not take any parameters.

1. `{{%/* table-row */%}}` takes content in between the opening and closing tags. There should be a number of `{{%/* table-row */%}}` tags equal to the number of column names, and values should appear in the same order as their labels do.

# Known Limitations

- `{{</* table */>}}` and `{{</* table-row */>}}` ***must*** use the `{{</**/>}}` syntax for shortcodes. Using `{{%/**/%}}` will cause the inner HTML to display inside a code block instead or rendering on the page. `{{%/* table-row */%}}` can use either, though `{{%/**/%}}` is recommended so you can use markdown inside of the cell.
- `{{%/* table-cell */%}}` tags must be on the same line as content, or else an issue occurs similar to the one above.
- Reference style markdown links (via `ref`, `relref`, and `static` shortcodes) cannot be used inside of `{{%/* table-cell */%}}` tags. Inline link syntax (`[link text](url)`) works fine.
- The shortcodes do not support `colspan`, `rowspan`, `<caption>`, or table footers. Then again, neither do markdown tables...
