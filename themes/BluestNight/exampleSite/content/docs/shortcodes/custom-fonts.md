+++
title = "Custom Fonts"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
aliases = ["/docs/shortcodes/handwriting/"]
[menu.main]
  weight = 1
  parent = "docs-shortcodes"
+++

Sometimes (sans-)serif fonts just don't cut it for what you're writing. You're posting a letter on your website and want it to look handwritten, or at least have the signature look handwritten. The `handwriting` shortcode provides you with a number of available handwriting fonts to achieve this effect.

<!--more-->

# Typewriter Font

A typewriter font is a little different from a monospace font in that it looks worn (and like it was typed on a typewriter).

{{% typewriter %}}
Alice was beginning to get very tired of sitting by her sister on
the bank, and of having nothing to do: once or twice she had
peeped into the book her sister was reading, but it had no pic-
tures or conversations in it, “and what is the use of a book,”
thought Alice, “without pictures or conversation?”
{{% /typewriter %}}

And here is the code that generated the above text:

```
{{%/* typewriter */%}}
Alice was beginning to get very tired of sitting by her sister on
the bank, and of having nothing to do: once or twice she had
peeped into the book her sister was reading, but it had no pic-
tures or conversations in it, “and what is the use of a book,”
thought Alice, “without pictures or conversation?”
{{%/* /typewriter */%}}
```

# Handwriting Fonts

```
{{%/* handwriting "font-name" */%}}
This text will look handwritten.
{{%/* /handwriting */%}}
```

Be sure to use `%%` and not `<>` as the one with `%` sends the content through the markdown parser, allowing you to still have bold, italics, etc. with your handwriting font. More [here](https://gohugo.io/extras/shortcodes/#shortcodes-with-markdown).

Available fonts are:

- `"allura"`
- `"calligraffiti"`
- `"dancing-script"`
- `"daniel"`
- `"euphoria-script"`
- `"journal"`
- `"kingthings-wrote"`
- `"note-this"`
- `"vag-handwritten"`

All fonts come from [FontSquirrel](https://www.fontsquirrel.com/), a website devoted to providing 100% free fonts, including for commercial use.
