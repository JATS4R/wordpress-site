---
ID: 311
post_title: Data Citations Recommendations
author: seligym@gmail.com
post_date: 2016-03-02 19:56:11
post_excerpt: ""
layout: page
permalink: >
  http://jats4r.org/data-citations-recommendations/
published: true
spacious_page_layout:
  - no_sidebar_content_centered
---
<h1 class="rec-heading">Data citations</h1>
<span class="status">Status: <strong><span style="color: #29cf84;">FINAL</span></strong></span>
<h2>Context</h2>
&lt;ref&gt; and elements contained therein.
<h2>Description</h2>
These recommendations contain best practices for tagging citations to data sets in a reference list.

<b>N.B.</b>
<ol>
	<li>These recommendations only apply to JATS 1.1d2 and forward, because the tags needed to make data citations machine readable are only available from 1.1d2 onwards.</li>
	<li>The following recommendations are specifically about citations related to data and data sets. <a href="http://jats4r.org/citations-recommendations">See JATS4R's recommendations for tagging citations in general</a>.</li>
</ol>
<h2>Additional reading</h2>
<ul>
	<li><a href="http://www.ncbi.nlm.nih.gov/books/NBK280240/">Adapting JATS to support data citation</a></li>
	<li><a href="https://www.force11.org/group/joint-declaration-data-citation-principles-final">Force 11 Joint Declaration on Data Citation Principles</a></li>
</ul>
<h2>Recommendations</h2>
<ol>
	<li><b>@publication-type="data" on &lt;mixed-citation&gt; or &lt;element-citation&gt;.</b> Use "data" as the value of @publication-type to indicate that the citation is to a data set, even if that data set is the entire data repository. <span style="color: #008080;">[[<a href="http://jats4r.org/validator/">Validator tool</a> result:  Error if @ not “data” and &lt;data-title&gt; is present]]</span></li>
	<li><b>@person-group-type on &lt;person-group&gt;.</b> As of version 1.1d2, the <a href="http://jats.nlm.nih.gov/publishing/tag-library/1.1d2/attribute/person-group-type.html">list of values for this attribute</a> includes 'curator', specifically to support data citations. Use “curator” whenever appropriate. <span style="color: #008080;">[[<a href="http://jats4r.org/validator/">Validator tool</a> result:  Info ]]</span></li>
	<li><b>&lt;data-title&gt; / &lt;source&gt;. </b>At least one of &lt;data-title&gt; or &lt;source&gt; must be present. &lt;data-title&gt; should hold the title of the data set. &lt;source&gt; should contain the name of the holding repository. Both should be present if applicable. <span style="color: #008080;">[[<a href="http://jats4r.org/validator/">Validator tool</a> result: Error if one not present  ]]</span></li>
	<li><b>&lt;year&gt;.</b> This should contain the 4-digit year the data was deposited. (Or in the case of data sets updated regularly, the year the data was used in the work in which it is being cited.). <span style="color: #008080;">[[<a href="http://jats4r.org/validator/">Validator tool</a> result: Error if year is not 4 digits  ]]</span></li>
	<li><b>&lt;pub-id&gt;.</b> This element should be used to hold both the repository ID for the data, in the element content, and, if applicable, the full URI to the data, in the @xlink:href attribute. The URI should be a DOI or similar persistent identifier. The @pub-id-type attribute must be used -- see the next recommendation for details. <span style="color: #008080;">[[<a href="http://jats4r.org/validator/">Validator tool</a> result: Info  ]]</span></li>
	<li><b>@pub-id-type on &lt;pub-id&gt;.</b>
In contrast to what is stated in the Tag Library (“Type of publication identifier or the organization or system that defined the identifier”) this attribute should <i>only</i> be used to state the type of identifier, and not to specify the organisation or system that defined the identifier . To specify the latter, use @assigning-authority (see the next recommendation). For example, a DOI that is assigned by CrossRef should have “doi” as the @pub-id-type, and “crossref” as the @assigning-authority.For many types of identifiers, there is only one assigning authority. For example, PubMed IDs are always assigned by the National Library of Medicine. In these cases, use @pub-id-type and not @assigning-authority.<span style="color: #008080;">[[<a href="http://jats4r.org/validator/">Validator tool</a> result:  Defer result pending the discussion of the <a href="https://github.com/JATS4R/JATS4R-Participant-Hub/issues/118">attribute value registry </a>]]</span></li>
	<li><b>@assigning-authority on &lt;pub-id&gt; and &lt;ext-link&gt;.</b> When the given type of identifier can be assigned by more than one organisation, and the organisation registering the identifier is known, include the @assigning-authority attribute on the &lt;pub-id&gt; element. Values might be, for example, “crossref” or “figshare”. Values should be in lowercase. <span style="color: #008080;">[[<a href="http://jats4r.org/validator/">Validator tool</a> result: Info for now; may change pending attribute value registry implementation]]</span></li>
	<li><b>@designator on &lt;version&gt;.</b> <b>(1.1d2+).</b> Use this attribute to contain the machine-readable version number of the dataset. The element contents can be a more human-readable note (see the example). <span style="color: #008080;">[[<a href="http://jats4r.org/validator/">Validator tool</a> result: error if not present ]]</span></li>
</ol>
<h2>Example</h2>
<pre>&lt;ref id="d1"&gt;
   &lt;element-citation publication-type="data"&gt;
      &lt;person-group person-group-type="author"&gt;
         &lt;collab&gt;The Concerto Consortium&lt;/collab&gt;
         &lt;name&gt;
            &lt;surname&gt;van Beethoven&lt;/surname&gt;
            &lt;given-names&gt;Ludwig&lt;/given-names&gt;
         &lt;/name&gt;
         &lt;name&gt;
            &lt;surname&gt;Liszt&lt;/surname&gt;
            &lt;given-names&gt;F&lt;/given-names&gt;
       &lt;/name&gt;
    &lt;/person-group&gt;
    &lt;person-group person-group-type="curator"&gt;
       &lt;name&gt;
          &lt;surname&gt;Bach&lt;/surname&gt;
          &lt;given-names&gt;JS&lt;/given-names&gt;
      &lt;/name&gt;
   &lt;/person-group&gt;
   &lt;data-title&gt;Title of data set&lt;/data-title&gt;
   &lt;year iso-8601-date="2014"&gt;2014&lt;/year&gt;
   &lt;source&gt;Repository Name&lt;/source&gt;
   &lt;pub-id pub-id-type="doi" assigning-authority="figshare" xlink:href="http://dx.doi.org/10.1234/1234321"&gt;10.1234/1234321&lt;/pub-id&gt;
   &lt;version designator="16.2"&gt;16th version, second release&lt;/version&gt;
   &lt;/element-citation&gt;
&lt;/ref&gt;

</pre>