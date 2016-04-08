---
ID: 340
post_title: Permissions recommendations
author: seligym@gmail.com
post_date: 2016-03-03 12:32:36
post_excerpt: ""
layout: page
permalink: >
  http://jats4r.org/permissions-recommendations/
published: true
spacious_page_layout:
  - no_sidebar_content_centered
---
<h1 class="rec-heading">Permissions</h1>
<span class="status">Status: <strong><span style="color: #29cf84;">FINAL</span></strong></span>
<h2>Context</h2>
&lt;permissions&gt; and child elements &lt;copyright-statement&gt;, &lt;copyright-year&gt;, &lt;copyright-holder&gt;, &lt;license&gt;, &lt;license-p&gt;, &lt;ali:free_to_read&gt;,  and &lt;ali:license_ref&gt;
<h2>Description</h2>
These recommendations contain best practices for indicating the permissions (copyright and licensing information) associated with an article as a whole, or with part of an article (such as a figure). <a href="#permissions-table">For a list of document objects and the corresponding elements to which &lt;permissions&gt; can apply, please see this table</a>. The permissions information associated with the whole document is contained within the article metadata.
<h2>Remarks:</h2>
<ol>
	<li>Per the JATS documentation, &lt;copyright-statement&gt; and &lt;license-p&gt; are intended for display purposes only, and are therefore not addressed by these recommendations because they are not intended to be mined for data. The &lt;license-p&gt; element is the domain for editorial information and context. Links to licenses might appear within these human-readable sections, but those links should not assumed to be machine readable, and should be ignored by automated processes. <span style="color: #008080;">[[Validator tool result: info]]</span></li>
	<li>In some cases, an article may contain document objects (such as figures or tables) that have licenses which are different from the license that applies to the article as a whole. For example, a CC-BY journal article might contain a figure reproduced from an article published under a non-CC-BY license. That figure must then contain a separate &lt;permissions&gt; element; every other article obThese recommendations contain best practices for indicating the permissions (copyright and licensing information) associated with an article as a whole, or with part of an article (such as a figure). For a list of document objects and the corresponding elements to which &lt;permissions&gt; can apply, please see this list. The permissions information associated with the whole document is contained within the article metadata.</li>
	<li>Article objects will be considered to inherit the permissions as set out in &lt;article-meta&gt;, which applies to the journal article as a whole. Multiple components of an article can have their own &lt;permissions&gt; element and, if tagged as such, each of these components would not inherit the permission set in the &lt;article-meta&gt;. The separate &lt;permissions&gt; provided for the component must be complete, containing &lt;copyright-statement&gt;, &lt;copyright-year&gt;, &lt;copyright-holder&gt;, and &lt;license&gt;.</li>
	<li>Concerning @license-type on &lt;license&gt; element: This attribute can be useful inside a closed system. However, in terms of reusing content, the values of this attribute have not been standardized (i.e., its values are not controlled and are therefore not usable by automated systems), so  it can’t be used to provide reliably useful information, and therefore a formal recommendation has not been made for this attribute here.  <span style="color: #008080;">[[Validator tool result: info]]</span></li>
</ol>
<h2>Recommendations</h2>
<ol>
	<li><b>&lt;permissions&gt;</b> <b>(permissions on the whole article)</b>. This element must be present within &lt;article-meta&gt;.<i>  </i><span style="color: #008080;">[[Validator tool result: Error ]]</span></li>
	<li><b> &lt;permissions&gt;</b> (<b>permissions on objects within an article)</b>. If any object within the article (for example, a figure or a table) has different permissions from the article as a whole, &lt;permissions&gt; must be included in that element to ensure the object does not inherit the permissions that apply to the document as a whole. (<a href="#permissions-table">See the complete list of article objects to which &lt;permissions&gt; can apply</a>). <span style="color: #008080;">[[Validator tool result: Info]]</span></li>
	<li><b>&lt;copyright-year&gt;</b> When a work is protected by copyright (i.e., the work is not in the public domain), this element should be used and should contain a full four-digit year with no whitespace. <span style="color: #008080;">[[Validator tool result: Error ]]</span></li>
	<li><b>&lt;copyright-holder&gt;</b> When a work is protected by copyright, this element should be used and should identify the person or institution that holds the copyright. <span style="color: #008080;">[[Validator tool result: Error]]</span></li>
	<li><b>@xlink:href on &lt;license&gt; or &lt;ali:license_ref&gt; (depending on the DTD version) </b>If a license is defined by a URI (for example, any of the Creative Commons licenses), this should be the sole place that a machine (or anyone) should need to look for the license URI.
<ol>
	<li>For JATS version 1.1d3 and forward, the license URI should be contained within <b>&lt;ali:license_ref&gt;</b>. <span style="color: #008080;">[[Validator tool result: Warning when &lt;ali:license_ref does not contain the URL for the license ]]</span></li>
	<li>For JATS version 1.1d2 and backward,  use the URI as the value of @xlink:href on &lt;license&gt;. <span style="color: #008080;">[[Validator tool result: Warning when &lt;license&gt; doesn’t have @xlink:</span>href<span style="color: #008080;">  ]]</span></li>
</ol>
</li>
	<li><b>@start_date attribute on &lt;ali:license_ref&gt;</b>. This attribute is only required if it differs from the publication date.</li>
	<li>&lt;license-p&gt; This element is not required, but is intended for human readable consumption so there are no guidelines for the content used within the tag. Not to be used for the machine-readable, canonical URI for the license. <span style="color: #008080;">[[Validator tool result: Info whenever &lt;license-p&gt; or &lt;p&gt; occurs inside &lt;license&gt; ]]</span></li>
	<li><b>&lt;ali:free_to_read&gt;</b> Content that is not behind access barriers, irrespective of any license specifications, should also contain this tag. It is used to indicate the content can be accessed by any user without payment or authentication.  If the content is only available for a certain period, then @start_date and @end_date attributes can be used to indicate this. <span style="color: #008080;">[[Validator tool result: Info]]</span></li>
</ol>
<h2>Examples</h2>
<b>Example 1: Permissions that apply to an entire journal article</b>

Example 1a: JATS version 1.1d3 and forward
<pre>&lt;article xmlns:ali="http://www.niso.org/schemas/ali/1.0" … &gt;
...
&lt;permissions&gt;
 &lt;copyright-statement&gt;© 2014 Surname et al.&lt;/copyright-statement&gt;
 &lt;copyright-year&gt;2014&lt;/copyright-year&gt;
 &lt;copyright-holder&gt;Surname et al.&lt;/copyright-holder&gt;
 &lt;ali:free_to_read/&gt;
 &lt;license&gt;
 &lt;ali:license_ref start_date="2014-02-03"
 &gt;http://creativecommons.org/licenses/by/4.0/&lt;/ali:license_ref&gt;
 &lt;license-p&gt;This is an open access article distributed under the terms of the &lt;ext-link
 ext-link-type="uri" xlink:href="http://creativecommons.org/licenses/by/4.0/"&gt;Creative
 Commons Attribution License&lt;/ext-link&gt;, which permits unrestricted use, distribution,
 reproduction and adaptation in any medium and for any purpose provided that it is properly
 attributed. For attribution, the original author(s), title, publication source (PeerJ) and
 either DOI or URL of the article must be cited.&lt;/license-p&gt;
 &lt;/license&gt;
&lt;/permissions&gt;
…
&lt;/article&gt;
</pre>
Example 1b: JATS version 1.1d2 and backward
<pre>&lt;permissions&gt;
 &lt;copyright-statement&gt;© 2014 Surname et al.&lt;/copyright-statement&gt;
 &lt;copyright-year&gt;2014&lt;/copyright-year&gt;
 &lt;copyright-holder&gt;Surname et al.&lt;/copyright-holder&gt;
 &lt;license xlink:href="http://creativecommons.org/licenses/by/4.0/"&gt;
 &lt;license-p&gt;This is an open access article distributed under the terms of the 
&lt;ext-link
 ext-link-type="uri" xlink:href="http://creativecommons.org/licenses/by/4.0/"&gt;Creative
 Commons Attribution License
&lt;/ext-link&gt;, which permits unrestricted use, distribution,
 reproduction and adaptation in any medium and for any purpose provided that it is properly
 attributed. For attribution, the original author(s), title, publication source (PeerJ) and
 either DOI or URL of the article must be cited.
&lt;/license-p&gt;
 &lt;/license&gt;
&lt;/permissions&gt;
</pre>
<b>Example 2: Permissions that apply to part of a work (e.g., a figure)</b>
<pre> 
&lt;fig id="fig1"&gt;
 &lt;label&gt;Fig. 1&lt;/label&gt;
 &lt;caption&gt;...&lt;/caption&gt;
 &lt;!--Here, this particular image is published under a copyright that is different from the one that applies to the article a whole (and is, in fact, all rights reserved).--&gt;
 &lt;permissions&gt;
 &lt;copyright-statement&gt;The National Portrait Gallery, London. All rights reserved&lt;/copyright-statement&gt;
 &lt;copyright-year&gt;2013&lt;/copyright-year&gt;
 &lt;!-- Note: no license element here: all rights reserved. --&gt;
 &lt;/permissions&gt;
 &lt;graphic xlink:href="images/fig1"/&gt;
 &lt;/fig&gt;
</pre>
<b>Example 3: Multiple permissions on a single article object (e.g, a figure)</b>

The following examples illustrates a case where a single, composite figure is the subject of two separate copyrights. In this case, multiple &lt;permissions&gt; elements are given for that figure. A machine attempting to parse this, to determine the re-usability of that figure, would have to pick the most restrictive of the licences (in this case, no licence, or “all rights reserved”).
<pre>&lt;article&gt;
 &lt;front&gt;
 ...
 &lt;permissions&gt;
 &lt;copyright-statement&gt;&amp;#xa9; 2012, Alegado et al&lt;/copyright-statement&gt;
 &lt;copyright-year&gt;2012&lt;/copyright-year&gt;
 &lt;copyright-holder&gt;Alegado et al&lt;/copyright-holder&gt;
 &lt;license xlink:href="http://creativecommons.org/licenses/by/4.0/"&gt;
 &lt;license-p&gt;This article is distributed under the terms of the &lt;ext-link
 ext-link-type="uri"
 xlink:href="http://creativecommons.org/licenses/by/4.0/"&gt;Creative
 Commons Attribution License&lt;/ext-link&gt;, which permits unrestricted use
 and redistribution provided that the original author and source are
 credited.&lt;/license-p&gt;
 &lt;/license&gt;
 &lt;/permissions&gt;
 ...
 &lt;/front&gt;
 &lt;body&gt;
 ...
 &lt;fig id="fig2" position="float"&gt;
 &lt;label&gt;Figure 2.&lt;/label&gt;
 &lt;caption&gt; . . . &lt;/caption&gt;
 &lt;graphic xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="elife00013f002"/&gt;
 &lt;permissions&gt;
 &lt;copyright-statement&gt;© 1977 Thieme Medical Publishers. All Rights
 Reserved.&lt;/copyright-statement&gt;
 &lt;copyright-year&gt;1977&lt;/copyright-year&gt;
 &lt;copyright-holder&gt;Thieme Medical Publishers&lt;/copyright-holder&gt;
 &lt;license&gt;
 &lt;license-p&gt;Figure 1, upper panel, is reproduced from
 &lt;xref ref-type="bibr" rid="bib45"&gt;Hughes and Sperandio, 2008&lt;/xref&gt;
 with permission.&lt;/license-p&gt;
 &lt;/license&gt;
 &lt;/permissions&gt;
 &lt;permissions&gt;
 &lt;copyright-statement&gt;&amp;#xa9; 2012, Alegado et al&lt;/copyright-statement&gt;
 &lt;copyright-year&gt;2012&lt;/copyright-year&gt;
 &lt;copyright-holder&gt;Alegado et al&lt;/copyright-holder&gt;
 &lt;license xlink:href="http://creativecommons.org/licenses/by/4.0/"&gt;
 &lt;license-p&gt;Figure 1, lower panel, is distributed under ...&lt;/license-p&gt;
 &lt;/license&gt;
 &lt;/permissions&gt;
 &lt;/fig&gt;
 ...
 &lt;/body&gt;
 ...
&lt;/article&gt;
</pre>
<h2 id="permissions-table">Where &lt;permissions&gt; may be applied in a document</h2>
Per the <a href="http://jatspan.org/niso/publishing-1.0/#p=elem-permissions">JATS schema</a>, the &lt;permissions&gt; element is allowed within many other elements.

The following table specifies what content is covered by a &lt;permissions&gt; element that appears in a given location.
<table>
<tbody>
<tr>
<td><b>Document object</b></td>
<td><b>Element that may contain &lt;permissions&gt; </b></td>
<td><b>What the permissions cover</b></td>
</tr>
<tr>
<td>Array</td>
<td>&lt;array&gt;</td>
<td>Self</td>
</tr>
<tr>
<td>Article as a whole</td>
<td>&lt;article&gt;</td>
<td>Closest parent article element</td>
</tr>
<tr>
<td>Boxed text</td>
<td>&lt;boxed-text&gt;</td>
<td>Self</td>
</tr>
<tr>
<td>Chemical structure</td>
<td>&lt;chem-struct-wrap&gt;</td>
<td>Self</td>
</tr>
<tr>
<td>Displayed quotation</td>
<td>&lt;disp-quote&gt;</td>
<td>Self</td>
</tr>
<tr>
<td>Figure</td>
<td>&lt;fig&gt;</td>
<td>The whole figure, and any associated files</td>
</tr>
<tr>
<td>Response or sub-article metadata</td>
<td>&lt;front-stub&gt;</td>
<td>The closest response or sub-article parent</td>
</tr>
<tr>
<td>Graphic</td>
<td>&lt;graphic&gt;</td>
<td>The image file (@xlink:href) - and its description</td>
</tr>
<tr>
<td>Media</td>
<td>&lt;media&gt;</td>
<td>The media file (@xlink:href) - and its description</td>
</tr>
<tr>
<td>Preformatted text</td>
<td>&lt;preformat&gt;</td>
<td>The contents of the element</td>
</tr>
<tr>
<td>Section metadata</td>
<td>&lt;sec&gt;</td>
<td>Closest parent sec element</td>
</tr>
<tr>
<td>Statement</td>
<td>&lt;statement&gt;</td>
<td>Self</td>
</tr>
<tr>
<td>Supplementary material</td>
<td>&lt;supplementary-material&gt;</td>
<td>The supplemental file (@xlink:href) - and its description</td>
</tr>
<tr>
<td>Tables and their captions</td>
<td>&lt;table-wrap&gt;</td>
<td>The table, caption, etc.</td>
</tr>
<tr>
<td>Tables, notes in the footer</td>
<td>&lt;table-wrap&gt;</td>
<td>Closest parent table-wrap element</td>
</tr>
<tr>
<td>Verse group</td>
<td>&lt;verse-group&gt;</td>
<td>Self</td>
</tr>
</tbody>
</table>