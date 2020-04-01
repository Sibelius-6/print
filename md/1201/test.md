---
title: Testing
layout: mdtoc
---
# inline math
&#92;(x=2 &#92;)

# display
&#92;[
    hey
&#92;]

# maxp

&#92;[
    &#92;begin{array}{ll}
    &#92;max & &#92;begin{array}{l}c^T x&#92;end{array}&#92;&#92;
    &#92;text{s.t.} & &#92;begin{array}{lll}
    Ax \le b &#92;&#92;
    x\ge 0
    &#92;end{array}
    &#92;end{array}
&#92;]

# minp

&#92;[
    &#92;begin{array}{ll}
    &#92;min & &#92;begin{array}{l}b^T y&#92;end{array}&#92;&#92;
    &#92;text{s.t.} & &#92;begin{array}{lll}
    A^T y\ge c &#92;&#92;
    y\ge 0
    &#92;end{array}
    &#92;end{array}
&#92;]

# cases
&#92;[
    x= &#92;begin{cases}
     0& &#92;text{if } x=0 &#92;&#92;
      x & &#92;text{otherwise}
    &#92;end{cases}
&#92;]

# brace
&#92;(&#92;left&#92;{ {1\over x}, {1\over x^2} &#92;right&#92;} &#92;)

# array
&#92;[
    &#92;begin{array}{llll}
    x &#92;&#92; y &#92;&#92; z &#92;&#92; w &#92;&#92;
    &#92;end{array}
&#92;]

# pmatrix
&#92;[
    &#92;begin{pmatrix}
    1 & 1 & 2 &#92;&#92;
    2 & 2 & 3 &#92;&#92;
    3 & 3 & 4
    &#92;end{pmatrix}
&#92;]

# fancy block testing
<div class="fancy-block"  data-type="Theorem" data-title="dumbtitle">
<div class="fancy-block-content">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
</div></div>

<div class="fancy-block"  data-type="Lemma" data-title="dumbtitle">
<div class="fancy-block-content">
    lemma with a title and with math: &#92;( x+y=z = \int_x^yf(x)~dx&#92;)
</div></div>

<div class="fancy-block" data-type="Proposition">
<div class="fancy-block-content">
    no title and with display math:&#92;[
        \sum_x^y f(s) \sigma
    &#92;]
</div></div>

<div class="fancy-block" data-type="Theorem" data-title="Farkas' Lemma">
<div class="fancy-block-content">
    &#92;[
        P=&#92;left&#92;{ x\in \mathbb R^n:Ax\le b &#92;right&#92;}=\emptyset \iff \exists u\in\mathbb R^m: &#92;begin{array}{llll}
        u^T A=0 &#92;&#92;
        u^T b<0 &#92;&#92;
        u\ge 0
        &#92;end{array}
    &#92;]
</div></div>

<div class="fancy-block"  data-type="Corollory">
<div class="fancy-block-content">
    Sample Corollory...
</div></div>
<div class="fancy-block" data-type="Definition" data-title="Line">
<div class="fancy-block-content">
    Let &#92;(\bar x,\bar d\in\mathbb R^n,\bar d\ne 0 &#92;). The set
    &#92;[
        &#92;left&#92;{ x\in\mathbb R^n:x=\bar x+\lambda d\text{ for some }\lambda \in \mathbb R &#92;right&#92;}
    &#92;]
is called a line.
</div></div>
