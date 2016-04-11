---
ID: 24
post_title: Why participate
author: seligym@gmail.com
post_date: 2015-12-01 16:32:12
post_excerpt: ""
layout: page
permalink: http://jats4r.org/why-participate/
published: true
spacious_page_layout:
  - no_sidebar_content_centered
---
<h1>Why participate in JATS4R?</h1>
<h2><strong>Because reusability affects everyone.</strong></h2>
Reusability is about making some key parts of XML consistent across all publishers, so that machines (and humans!) can efficiently process, exchange, store, and retrieve that content. <a href="http://jats4r.org/how-to-participate">Find out more about how organizations are participating in JATS4R</a>.
<h2>But we already use JATS  XML. Isn't that enough?</h2>
While <a href="http://jats.nlm.nih.gov/index.html" target="_blank">JATS</a> is the XML standard that virtually everyone in scholarly publishing uses today, it is also quite loose. This means that the same content can be marked up in many different ways, which makes it harder for machines and humans alike to predictably and accurately find key pieces of information.

For example, the following are two different ~but valid!~ ways of indicating licensing information using JATS, which machine-reading systems need to find in order to reuse content:
<div class="examples">
<div class="ex-left">
<p style="color: #145fcd; margin-bottom: 0px;">One way</p>
<p class="taggedtext">&lt;permissions&gt;
&lt;license&gt;
&lt;license-p&gt;
<span style="color: #ffcc00;"><strong>http://creativecommons.org/licenses/by/2.0/</strong></span>
&lt;/license-p&gt;
&lt;/license&gt;
&lt;/permissions&gt;</p>

</div>
<div class="ex-right">
<p style="color: #145fcd; margin-bottom: 0px;">Another way (<a href="http://jats4r.org/permissions-recommendations">See JATS4R recommendations</a>)</p>
<p class="taggedtext">&lt;permissions&gt;
&lt;license license-type="open-access" xlink:href="<span style="color: #ffcc00;"><strong>http://creativecommons.org/licenses/by/2.0/</strong></span>"&gt;
&lt;license-p&gt;This is an open-access article distributed under the terms of the Creative Commons Attribution License, which permits unrestricted use, distribution, and reproduction in any medium, provided the original work is properly cited.
&lt;/license-p&gt;
&lt;/license&gt;
&lt;/permissions&gt;</p>

</div>
</div>
<div style="clear: both; background-color: #deecf8; margin-top: -20px;">
<p style="line-height: 160%; font-weight: bold; padding: 20px;">By adopting JATS4R recommendations for XML best tagging practices, we can lower the barrier to our content's reuse by the systems that handle scholarly publishing content today, such as web platforms, libraries, repositories, aggregator sites, digital catalogs, and content-discovery platforms. A little participation in JATS4R can make a big difference. <strong><a href="http://jats4r.org/how-to-participate/">Find out how you can get involved.</a></strong></p>

</div>