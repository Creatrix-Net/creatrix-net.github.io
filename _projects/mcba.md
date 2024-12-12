---
layout: distill
title: Mind Controlled Bionic Arm with Sense of Touch
description: Imagine a prosthetic arm that functions like your natural arm. You wear a headband, and with the thought process, the working signal from mind connects to the prosthetic about moving the arm, it responds accordingly—just like your real arm!
tags: distill formatting
giscus_comments: true
img: /assets/img/mcba_logo.jpeg
date: 2024-12-12
featured: true
importance: 1
category: work
mermaid:
  enabled: true
  zoomable: true
code_diff: true
chart:
  chartjs: true
  echarts: true
  vega_lite: true
tikzjax: true
typograms: true

authors:
  - name: Dhruva Shaw
    url: "https://dhruvashaw.in"
    affiliations:
      name: Creative Net
  - name: Arittrabha Sengupta
    url: "https://arittrabha-biotech.pages.dev"
    affiliations:
      name: Creative Net
  - name: Jay Baswaraj Khaple
    url: "mailto:khaplejay00@gmail.com"
    affiliations:
      name: Lovely Professional University
  - name: Bhavya Choudhary
    url: "mailto:choudharybhavya225@gmail.com"
    affiliations:
      name: Lovely Professional University
  - name: Dr. G. Raam Dheep
    url: "mailto:raam.25227@lpu.co.in"
    affiliations:
      name: Lovely Professional University

# bibliography: 2018-12-22-distill.bib

# Optionally, you can add a table of contents to your post.
# NOTES:
#   - make sure that TOC names match the actual section names
#     for hyperlinks within the post to work correctly.
#   - we may want to automate TOC generation in the future using
#     jekyll-toc plugin (https://github.com/toshimaru/jekyll-toc).
toc: true

# Below is an example of injecting additional post-specific styles.
# If you use this post as a template, delete this _styles block.
_styles: >
  .fake-img {
    background: #bbb;
    border: 1px solid rgba(0, 0, 0, 0.1);
    box-shadow: 0 0px 4px rgba(0, 0, 0, 0.1);
    margin-bottom: 12px;
  }
  .fake-img p {
    font-family: monospace;
    color: white;
    text-align: left;
    margin: 12px 0;
    text-align: center;
    font-size: 16px;
  }
---

## Equations

This theme supports rendering beautiful math in inline and display modes using [MathJax 3](https://www.mathjax.org/) engine.
You just need to surround your math expression with `$$`, like `$$ E = mc^2 $$`.
If you leave it inside a paragraph, it will produce an inline expression, just like $$ E = mc^2 $$.

In fact, you can also use a single dollar sign `$` to create inline formulas, such as `$ E = mc^2 $`, which will render as $ E = mc^2 $. This approach provides the same effect during TeX-based compilation, but visually it appears slightly less bold compared to double-dollar signs `$$`, making it blend more naturally with surrounding text.

To use display mode, again surround your expression with `$$` and place it as a separate paragraph.
Here is an example:

$$
\left( \sum_{k=1}^n a_k b_k \right)^2 \leq \left( \sum_{k=1}^n a_k^2 \right) \left( \sum_{k=1}^n b_k^2 \right)
$$

Note that MathJax 3 is [a major re-write of MathJax](https://docs.mathjax.org/en/latest/upgrading/whats-new-3.0.html) that brought a significant improvement to the loading and rendering speed, which is now [on par with KaTeX](http://www.intmath.com/cg5/katex-mathjax-comparison.php).
