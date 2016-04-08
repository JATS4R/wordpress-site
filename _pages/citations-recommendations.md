---
ID: 480
post_title: Citations recommendations
author: seligym@gmail.com
post_date: 2016-03-10 16:02:45
post_excerpt: ""
layout: page
permalink: >
  http://jats4r.org/citations-recommendations/
published: true
spacious_page_layout:
  - no_sidebar_content_centered
---
<h1 class="rec-heading">Citations (general)</h1>
<span class="status">Status: <span style="color: #ff9900;"><strong>DRAFT</strong></span></span>
<h2>Context</h2>
&lt;ref&gt; and elements contained therein.
<h2>Description</h2>
These recommendations contain best practices for tagging citations in general.

<b>N.B. </b><a href="http://jats4r.org/data-citations-recommendations">For specific recommendations on tagging data citations, see the Data Citations page</a>.
<h2>Additional reading</h2>
See the <a href="http://jats.nlm.nih.gov/archiving/tag-library/1.1d3/chapter/tag-citation.html">JATS tag library documentation</a> for a collection of best practices for tagging citations.
<h2>Recommendations</h2>
<ol>
	<li><strong>&lt;ref id="..."&gt;</strong>. Use a separate &lt;ref&gt; element for each citation. Use a unique and internally consistent identifier for @id. Best practice is an alphanumeric sequence common to all citations in your document, followed by an incremental number matching the sequential order of citations.
&lt;mixed-citation&gt; / &lt;element-citation&gt;. Either of these elements could be used, depending on whether your practice is to include punctuation in your XML (&lt;mixed-citation&gt;) or to generate punctuation (&lt;element-citation&gt;).</li>
	<li><strong>@publication-type="..." on &lt;mixed-citation&gt; or &lt;element-citation&gt;</strong>. Use "journal" or “book” as the value of @publication-type to indicate that the citation is to a journal or book, respectively. Other examples are: “letter”, “review”, “patent”, “report”, “standard”, “data”, “working-paper”. This list is not exhaustive and is sourced from the JATS guidelines. This is not a limited field so others can be used as appropriate, for example, “website”. However, in the interests of standardisation, JATS4R requests publishers to contact JATS4R if using additional values so we can create a definitive list and reduce variation across XML sources. “Other” is not a preferred value.</li>
	<li><strong>&lt;person-group&gt; and @person-group-type</strong>. Use the &lt;person-group&gt; element to specify authors and other contributors in a citation. Use the @person-group-type attribute to specify the role of a contributor, when it is possible to identify them with a role. A separate &lt;person-group&gt; element should be used for each role. This attribute has a fixed list of allowed values in the Journal Publishing tag set: all-authors; assignee; author; compiler; curator; director; editor; guest-editor; inventor; transed; translator.</li>
	<li><strong>&lt;name&gt; / &lt;string-name&gt; / &lt;collab&gt;</strong>. The &lt;name&gt; or &lt;string-name&gt; element should be used for an individual named author. Use &lt;name&gt; when the parent element is &lt;element-citation&gt;, and &lt;string-name&gt; when the parent is &lt;mixed-citation&gt;. When groups of authors (consortia) are cited under a group name or an institution is cited as the contributor, the &lt;collab&gt; element should be used.</li>
	<li><strong>&lt;article-title&gt;</strong>. This is used for the article title for journal references. The journal title should be contained within &lt;source&gt;.</li>
	<li><strong>&lt;data-title&gt;</strong>. This newly added element (tag set version 1.1d2) should be used for the title of data citations; for tag set versions 1.1d1 and lower, use &lt;source&gt;.</li>
	<li><strong>&lt;source&gt;</strong>. This is used for the book title for book references and journal titles for journal references.</li>
	<li><strong>&lt;year&gt;</strong>. This should contain the 4-digit year of publication. If the element contains anything other than a single 4-digit year (such as, for example, “2012A”, “2005Q1”), then use the @iso-8601-date attribute to specify the 4-digit year.</li>
	<li><strong>&lt;pub-id&gt;</strong>. This text content of this element should be used to hold a formal identifier, such as a DOI, of the cited work. The @pub-id-type attribute must be used -- see the next recommendation.
<p class="list-note-title" style="margin:10px 0px 5px 0px"><em><strong>A note on DOIs</strong></em>:</p>
<p>When specifying a DOI, in the contents of the element, use the DOI “name”, which is the non-URI form of the identifier (beginning with “10.”). If a URL for the work is known, that can be included in the @xlink:href attribute, for display purposes only. In other words, the machine-readable, canonical identifier should be given in the text content, and machines ingesting the metadata should look for the identifier there.</p>
<p>A DOI should be tagged as follows:
&lt;pub-id pub-id-type="doi" assigning-authority="crossref" xlink:href="http://doi.org/10.1234/1234321"&gt;10.1234/1234321&lt;/pub-id&gt;</p>
</li>
	<li><strong>@pub-id-type on &lt;pub-id&gt;</strong>. Use this attribute to specify the type of the identifier. For example, a DOI would have the @pub-id-type value of “doi”. The value should be one of the valid values from the list in the Tag Library.</li>
	<li><strong>&lt;fpage&gt;, &lt;lpage&gt; and &lt;elocation-id&gt;</strong>. The first and last page elements should be used for traditional print publications. The last page should always exceed the number used in the first page, ie editorial style of shortening the last page value should not be used as that is only useful for human readability and not for machine consumption. Many non-print products will not have first and last page values, but a unique number that is called the elocation-id; in these instances, the &lt;fpage&gt; and &lt;lpage&gt; values should not be used but replaced with an &lt;elocation-id&gt;.</li>
</ol>
<h2>Examples</h2>
<pre> &lt;ref id="bib13"&gt;
      &lt;element-citation publication-type="journal"&gt;
           &lt;person-group person-group-type="author"&gt;
                  &lt;name&gt;
                      &lt;surname&gt;Bradley&lt;/surname&gt;
                      &lt;given-names&gt;RK&lt;/given-names&gt;
                  &lt;/name&gt;
                  &lt;name&gt;
                     &lt;surname&gt;Roberts&lt;/surname&gt;
                     &lt;given-names&gt;A&lt;/given-names&gt;
                 &lt;/name&gt;
           &lt;/person-group&gt;
           &lt;year iso-8601-date="2009"&gt;2009&lt;/year&gt;
           &lt;article-title&gt;Fast statistical alignment&lt;/article-title&gt;
           &lt;source&gt;PLOS Computational Biology&lt;/source&gt;
           &lt;volume&gt;5&lt;/volume&gt;
           &lt;elocation-id&gt;e1000392&lt;/elocation-id&gt;
           &lt;pub-id pub-id-type="doi"&gt;10.1371/journal.pcbi.1000392&lt;/pub-id&gt;
      &lt;/element-citation&gt;
&lt;/ref&gt; 
</pre>