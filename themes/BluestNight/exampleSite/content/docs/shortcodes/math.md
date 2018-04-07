+++
title = "Math Typesetting"
hide_authorbox = true
disable_comments = true
categories = ["Documentation"]
[menu.main]
  weight = 2
  parent = "docs-shortcodes"
+++

BluestNight comes with support for LaTeX-like equation typesetting powered by [KaTeX](https://khan.github.io/KaTeX/).

# Usage

To stick as close as possible to the syntax used by LaTeX and recommended by KaTeX, you use the `{{</* math */>}}` shortcode to mark text to be rendered as math. Be sure to view the [syntax](https://khan.github.io/KaTeX/function-support.html) used by KaTeX.

```
An inline equation: {{</* math */>}}y = mx + b{{</* /math */>}}
```

An inline equation: {{< math >}}y = mx + b{{< /math >}}

```
A block-display equation:
{{</* math */>}}
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
{{</* /math */>}}
```

A block-display equation:
{{< math >}}
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
{{< /math >}}

# Why Another Shortcode?

It was possible to implement KaTeX without creating a new shortcode for it, however I found myself frustrated with the implementation that way.

Without the shortcode, to correctly render multiple lines of math, I had to do this in my markdown:

```
$$x = 1$$
$$x = 2$$
$$x = 3$$
$$x = 4$$
$$x = 5$$
$$x = 6$$
```

With the shortcode, I don't need to type the dollar signs (they are automatically added by the shortcode).

```
{{</* math */>}}
x = 1
x = 2
x = 3
x = 4
x = 5
x = 6
{{</* /math */>}}
```

# Why Not MathJax?

The biggest reason is speed. When tested using [this comparison demo](https://www.intmath.com/cg5/katex-mathjax-comparison.php), MathJax took over two seconds (> 2000 ms) to render the LaTeX code while KaTeX took only 86 ms.

A secondary concern is that MathJax makes use of JavaScript's `eval()` function, which is generally [considered unsafe](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval#Don't_use_eval_needlessly!) and something to avoid. KaTeX, on the other hand, does not use `eval()`.