---
ID: 441
post_title: Math recommendations
author: seligym@gmail.com
post_date: 2016-03-10 14:07:35
post_excerpt: ""
layout: page
permalink: http://jats4r.org/math-recommendations/
published: true
spacious_page_layout:
  - no_sidebar_content_centered
---
<h1 class="rec-heading">Math</h1>
<span class="status">Status: <span style="color: #29cf84;"><strong>FINAL</strong></span></span>
<h2>Context</h2>
&lt;disp-formula&gt; or &lt;inline-formula&gt; and elements contained therein.
<h2>Description</h2>
These recommendations contain best practices for tagging math. Inline equations are those in the flow of the text, usually within a sentence. Displayed equations are block-level (i.e., on their own line, as a block quote would be).
<h2>Remark on using images to represent math</h2>
The use of images to represent mathematical expressions is strongly discouraged. Math should be marked up within &lt;inline-formula&gt; and &lt;disp-formula&gt; using either &lt;tex-math&gt; or &lt;mml:math&gt;. If a graphical version of a mathematical expression is needed because of display requirements, &lt;alternatives&gt; should be used. See recommendation No. 1.

The only instance in which the graphic representation of a mathematical expression should be used outside of &lt;alternatives&gt; and without the equivalent mark-up is where that expression is so complicated that it cannot be represented in mark-up at all.&lt;/&gt;
<h2>Recommendations</h2>
<ol>
	<li><b>&lt;alternatives&gt;.</b> This element may contain any combination of representations (&lt;graphic&gt;, &lt;mml:math&gt;, &lt;tex-math&gt;), but at most one of each. And, where used, each representation should be correct, complete and logically equivalent with every other representation present. There is no explicit or implied preferred representation within &lt;alternatives&gt;. &lt;alternatives&gt; should placed within &lt;inline-formula&gt; or &lt;disp-formula&gt; and should contain the graphical version within &lt;inline-graphic&gt; (for an &lt;inline-formula&gt;) or &lt;graphic&gt; (for a &lt;disp-formula&gt;) alongside the equivalent &lt;mml:math&gt; or &lt;tex-math&gt; mark-up. See example 1.</li>
	<li><b>&lt;tex-math&gt;.</b> Use this element to contain math-mode LaTeX, <em>without</em> the delimiters that are normally used to switch into and out of math mode (<code>\\[...\\]</code>, <code>\\(...\\)</code>, <code>$$...$$</code>, etc.).
<ol class="sub-rec">
	<li><em>Rationale:</em> the TeX enclosed in the &lt;tex-math&gt; element is only used within JATS articles to produce mathematics, so specifying that the content is in math-mode precludes ambiguities that could arise if more general-purpose TeX structures were included (such as, for example, commands to produce tables of contents).</li>
	<li><em>Exception</em>: The only exception to this recommendation is that a subset of the LaTeX environments can be used to wrap the entire contents. (These are normally not permitted in math-mode.) These are typically used to specify alignment for multi-line equations. These are of the form <code>\begin{XXX} ... \end{XXX}</code>. Those environments that are permitted by MathJax are also allowed within the &lt;tex-math&gt; element; see <a href="http://docs.mathjax.org/en/latest/tex.html#environments" target="_blank">MathJax TeX and LaTeX Support - Environments</a> for a list.</li>
	<li><em>Note</em>: XML CDATA sections can be used to aid in embedding TeX markup within the XML of a JATS document. This obviates the need to use escape sequences such as <code>&amp;amp;</code> for an ampersand.</li>
	<li><em>TeX Macros</em>: TeX macros can be defined in a &lt;custom-meta&gt; element, with the &lt;meta-name&gt; element value set to “tex-math-definitions”. The macros defined within this element could then be used in any TeX equation within the article.</li>
</ol>
</li>
</ol>
<h2>Examples</h2>
<b>Example 1: A single equation in three alternative, equivalent forms (TeX, mathML, and graphic)</b>
<pre>&lt;p&gt;This was calculated as follows:
    &lt;inline-formula id="M1"&gt;
      &lt;alternatives&gt;
          &lt;tex-math&gt;a=b&lt;/tex-math&gt;
          &lt;mml:math&gt;
             &lt;mml:mi&gt;a&lt;/mml:mi&gt;
             &lt;mml:mo&gt;=&lt;/mml:mo&gt;
             &lt;mml:mi&gt;b&lt;/mml:mi&gt;
          &lt;/mml:math&gt;
          &lt;inline-graphic xlink:href="equation_M1.gif"/&gt;
      &lt;/alternatives&gt;
 &lt;/inline-formula&gt; 
...
&lt;/p&gt;</pre>
<b>Example 2: TeX </b>

<strong>2a</strong>. In almost all cases, use math-mode LaTeX without the delimiters that are normally used to switch into and out of math mode (<code>\\[...\\]</code>, <code>\\(...\\)</code>, <code>$$...$$</code>, etc.).
<pre> &lt;disp-formula&gt;
    &lt;tex-math id='M1'&gt;a = b&lt;/tex-math&gt;
 &lt;/disp-formula&gt;
</pre>
<strong>2b</strong>. Exception: using a subset of the LaTeX environments to wrap the entire contents.
<pre> &lt;disp-formula&gt;
    &lt;tex-math id='M1'&gt;
       \begin{align*}
       x^2 + y^2 &amp;amp; = 1\\
       x &amp;amp; = \sqrt{1-y^2}
       \end{align*}
    &lt;/tex-math&gt;
&lt;/disp-formula&gt;
</pre>
<strong>2c</strong>. XML CDATA section used to aid in embedding TeX markup.
<pre>&lt;disp-formula&gt;
&lt;tex-math id='M1'&gt;
&lt;<span style="color: #ff9900;">![CDATA[</span>
\begin{align*}
x^2 + y^2 &amp; = 1\\
x &amp; = \sqrt{1-y^2}
\end{align*}
<span style="color: #ff9900;">]]</span>&gt;
&lt;/tex-math&gt;
&lt;/disp-formula&gt;</pre>
<strong>2d</strong>. TeX macro defined in a &lt;custom-meta&gt; element.
<pre>&lt;article-meta&gt;
  ...
  &lt;custom-meta&gt;
     &lt;meta-name&gt;tex-math-definitions&lt;/meta-name&gt;
     &lt;meta-value&gt;
        \def\rmi{\rm i}
        \def\rme{\rm e}
     &lt;/meta-value&gt;
  &lt;/custom-meta&gt;
&lt;/article-meta&gt;
</pre>