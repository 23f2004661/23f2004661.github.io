---
layout: post
title: "Linear Transformation & Matrices"
date: "2026-10-22"
description: "Understanding a Matrices as Linear Transformations"
tags: [Linear Algebra, Math]
categories: [Linear Algebra]
toc:
  beginning: true
math: true
---

<!--
CHEAT SHEET

Inline math: \( [INLINE MATH] \) or $[INLINE MATH]$
Display math: \[ [DISPLAY MATH] \] or $$ [DISPLAY MATH] $$

Theorem / lemma / definition / proof / remark / note / example:
{% raw %}
<div class="theorem-box" markdown="1">
**Theorem.** [STATEMENT]
</div>
{% endraw %}
Use theorem-box, lemma-box, definition-box, proof-box, remark-box, note-box,
or example-box as the class. Put &#x220E; at the end of a proof for QED.

Figure:
{% raw %}{% include figure.liquid path="assets/img/[IMAGE FILE]" alt="[IMAGE DESCRIPTION]" caption="[FIGURE CAPTION]" %}{% endraw %}

Code block:
```python
# WRITE CODE HERE
```

Footnote reference and definition:
[FOOTNOTE REFERENCE][^note]
[^note]: [FOOTNOTE TEXT]
-->

## Introduction
<!-- WRITE HERE: intro / motivation -->
We learn about Matrices as a grid of numbers in our high school and our asked to calculate its determinant and do matrix multiplication but trust me it has a bigger purpose to serve in this world. The whole theory of Linear Algebra was created to help us understand the sturcture in the system that is under scrutiny, One such example is the class of linear dynamical systems (Systems that change linearly over time) examples would be.

- Markov chains (eg. Weather Forecasting)
- Leslie Model (eg. Population growth)
- predicting Fibonnaci Series
- Gradient Descent in Machine Learning

I will be talking about applications of Matrices and Linear Algebra in Machine Learning which is the most fundamental concept one needs to grasp before they can understand the nuances that go into understanding the world through data i.e Machine Learning.

---

## Where the basis vectors land

<div class="definition-box" markdown="1">
**Definition.** A map \(T\) is *linear* if
$$T(\mathbf{u} + \mathbf{v}) = T(\mathbf{u}) + T(\mathbf{v})
\quad\text{and}\quad T(c\mathbf{v}) = c\,T(\mathbf{v}).$$
</div>

Geometrically, grid lines stay parallel and evenly spaced, and the origin
stays fixed.


---

## [MAIN SECTION TITLE]
<!-- WRITE HERE: main section -->

### [SUBSECTION TITLE]
<!-- WRITE HERE: subsection -->

{% comment %}
## Interactive Visualization (optional)

{% include widget.liquid src="assets/widgets/[WIDGET FILE].html" title="[WIDGET TITLE]" %}
{% endcomment %}

---

## Footnotes
<!-- WRITE HERE: references and footnote definitions -->
