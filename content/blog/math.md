+++
author = "David Freddy"
categories = ["math"]
date = 2019-03-08T00:00:00Z
description = "A brief guide to setup KaTeX"
images = ["img/math.jpg"]
math = "true"
tags = ["markdown", "text"]
title = "Math Typesetting"

+++
HTML tags in markdown

https://jdhao.github.io/2019/12/29/hugo_html_not_shown/

Mathematical notation in a Hugo project can be enabled by using third party JavaScript libraries.

<!--more-->

In this example we will be using [KaTeX](https://katex.org/)

- Create a partial under `/layouts/partials/math.html`
- Within this partial reference the [Auto-render Extension](https://katex.org/docs/autorender.html) or host these scripts locally.
- Include the partial in your templates like so:

```
{{ if or .Params.math .Site.Params.math }}
{{ partial "math.html" . }}
{{ end }}
```

- To enable KaTex globally set the parameter `math` to `true` in a project's configuration
- To enable KaTex on a per page basis include the parameter `math: true` in content files.

**Note:** Use the online reference of [Supported TeX Functions](https://katex.org/docs/supported.html)

<h3>sadsa</h3>

<!-- KaTeX -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.10.1/dist/katex.min.css" integrity="sha384-dbVIfZGuN1Yq7/1Ocstc1lUEm+AT+/rCkibIcC/OmWo5f0EA48Vf8CytHzGrSwbQ" crossorigin="anonymous">
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.10.1/dist/katex.min.js" integrity="sha384-2BKqo+exmr9su6dir+qCw08N2ZKRucY4PrGQPPWU1A7FtlCGjmEGFqXCv5nyM5Ij" crossorigin="anonymous"></script>
<script defer src="https://cdn.jsdelivr.net/npm/katex@0.10.1/dist/contrib/auto-render.min.js" integrity="sha384-kWPLUVMOks5AQFrykwIup5lo0m3iMkkHrD0uJ4H5cjeGihAutqP0yW0J6dpFiVkI" crossorigin="anonymous" onload="renderMathInElement(document.body);"></script>

### Examples

Inline math: $$ \varphi = \dfrac{1+\sqrt5}{2}= 1.6180339887… $$

Block math:

$$
 \varphi = 3+\frac{1} {1+\frac{1} {1+\frac{1} {1+\cdots} } }
$$

Block math 2:

$$
 \boxed{\pi=\frac c d}
$$

$$
 f(a,b,c) = (a^2+b^2+c^2)^3
$$

$$
 \sum_{i=1}^\infty\frac{1}{n^2}=\frac{\pi^2}{6}
$$