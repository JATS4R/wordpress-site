---
ID: 311
post_title: Data Citations Recommendations
author: Mary Seligy
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
<h2>Examples</h2>
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
The following examples are from eLife:

<pre> &lt;?xml version="1.0" encoding="UTF-8"?&gt;
 &lt;!--Data reference: Dryad dataset --&gt;
 &lt;ref id="bib8"&gt;
 &lt;element-citation publication-type="data"&gt;
 &lt;person-group person-group-type="author"&gt;
 &lt;name&gt;
 &lt;surname&gt;Kok&lt;/surname&gt;
 &lt;given-names&gt;K&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Ay&lt;/surname&gt;
 &lt;given-names&gt;A&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Li&lt;/surname&gt;
 &lt;given-names&gt;L&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Arnosti&lt;/surname&gt;
 &lt;given-names&gt;DN&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;/person-group&gt;
 &lt;year iso-8601-date="2015"&gt;2015&lt;/year&gt;
 &lt;data-title&gt;Data from: Genome-wide errant targeting by Hairy&lt;/data-title&gt;
 &lt;source&gt;Dryad Digital Repository&lt;/source&gt;
 &lt;pub-id pub-id-type="doi" assigning-authority="Dryad Digital Repository"
 xlink:href="http://datadryad.org/resource/doi:10.5061/dryad.cv323"
 &gt;10.5061/dryad.cv323&lt;/pub-id&gt;
 &lt;/element-citation&gt;
 &lt;/ref&gt;
 &lt;!--Data reference: RCSB Protein Data Bank --&gt;
 &lt;ref id="bib9"&gt;
 &lt;element-citation publication-type="data"&gt;
 &lt;person-group person-group-type="author"&gt;
 &lt;name&gt;
 &lt;surname&gt;Du&lt;/surname&gt;
 &lt;given-names&gt;J&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Johnson&lt;/surname&gt;
 &lt;given-names&gt;LM&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Groth&lt;/surname&gt;
 &lt;given-names&gt;M&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Feng&lt;/surname&gt;
 &lt;given-names&gt;S&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Hale&lt;/surname&gt;
 &lt;given-names&gt;CJ&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Li&lt;/surname&gt;
 &lt;given-names&gt;S&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Vashisht&lt;/surname&gt;
 &lt;given-names&gt;AA&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Gallego-Bartolome&lt;/surname&gt;
 &lt;given-names&gt;J&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Wohlschlegel&lt;/surname&gt;
 &lt;given-names&gt;JA&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Patel&lt;/surname&gt;
 &lt;given-names&gt;DJ&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Jacobsen&lt;/surname&gt;
 &lt;given-names&gt;SE&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;/person-group&gt;
 &lt;year iso-8601-date="2014"&gt;2014&lt;/year&gt;
 &lt;data-title&gt;Crystal structure of KRYPTONITE in complex with mCHH DNA and
 SAH&lt;/data-title&gt;
 &lt;source&gt;RCSB Protein Data Bank&lt;/source&gt;
 &lt;pub-id pub-id-type="doi" assigning-authority="RCSB Protein Data Bank"
 &gt;10.2210/pdb4qen/pdb&lt;/pub-id&gt;
 &lt;/element-citation&gt;
 &lt;/ref&gt;
 &lt;!--Data reference: ProteomeXchange: pub-id-type="archive" - not clear what this number is, so default option --&gt;
 &lt;ref id="bib10"&gt;
 &lt;element-citation publication-type="data"&gt;
 &lt;person-group person-group-type="author"&gt;
 &lt;name&gt;
 &lt;surname&gt;Radoshevich&lt;/surname&gt;
 &lt;given-names&gt;L&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Impens&lt;/surname&gt;
 &lt;given-names&gt;F&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Ribet&lt;/surname&gt;
 &lt;given-names&gt;D&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Quereda&lt;/surname&gt;
 &lt;given-names&gt;JJ&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Nam Tham&lt;/surname&gt;
 &lt;given-names&gt;T&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Nahori&lt;/surname&gt;
 &lt;given-names&gt;MA&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Bierne&lt;/surname&gt;
 &lt;given-names&gt;H&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Dussurget&lt;/surname&gt;
 &lt;given-names&gt;O&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Pizarro-Cerdá&lt;/surname&gt;
 &lt;given-names&gt;J&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Knobeloch&lt;/surname&gt;
 &lt;given-names&gt;KP&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Cossart&lt;/surname&gt;
 &lt;given-names&gt;P&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;/person-group&gt;
 &lt;year iso-8601-date="2015"&gt;2015a&lt;/year&gt;
 &lt;data-title&gt;ISG15 counteracts &lt;italic&gt;Listeria monocytogenes&lt;/italic&gt;
 infection&lt;/data-title&gt;
 &lt;source&gt;ProteomeXchange&lt;/source&gt;
 &lt;pub-id pub-id-type="archive"
 xlink:href="http://proteomecentral.proteomexchange.org/cgi/GetDataset?ID=PXD001805"
 &gt;PXD001805&lt;/pub-id&gt;
 &lt;/element-citation&gt;
 &lt;/ref&gt;
 &lt;!--Data reference: ArrayExpress: pub-id-type="accession"--&gt;
 &lt;ref id="bib11"&gt;
 &lt;element-citation publication-type="data"&gt;
 &lt;person-group person-group-type="author"&gt;
 &lt;name&gt;
 &lt;surname&gt;Radoshevich&lt;/surname&gt;
 &lt;given-names&gt;L&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Impens&lt;/surname&gt;
 &lt;given-names&gt;F&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Ribet&lt;/surname&gt;
 &lt;given-names&gt;D&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Quereda&lt;/surname&gt;
 &lt;given-names&gt;JJ&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Nam Tham&lt;/surname&gt;
 &lt;given-names&gt;T&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Nahori&lt;/surname&gt;
 &lt;given-names&gt;MA&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Bierne&lt;/surname&gt;
 &lt;given-names&gt;H&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Dussurget&lt;/surname&gt;
 &lt;given-names&gt;O&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Pizarro-Cerdá&lt;/surname&gt;
 &lt;given-names&gt;J&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Knobeloch&lt;/surname&gt;
 &lt;given-names&gt;KP&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Cossart&lt;/surname&gt;
 &lt;given-names&gt;P&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;/person-group&gt;
 &lt;year iso-8601-date="2015"&gt;2015b&lt;/year&gt;
 &lt;article-title&gt;Transcription profiling by high throughput sequencing of LoVo
 cells infected with Listeria for 24 hr compared to uninfected
 cells&lt;/article-title&gt;
 &lt;source&gt;ArrayExpress&lt;/source&gt;
 &lt;pub-id pub-id-type="accession"
 xlink:href="https://www.ebi.ac.uk/arrayexpress/experiments/E-MTAB-3649/"
 &gt;E-MTAB-3649&lt;/pub-id&gt;
 &lt;/element-citation&gt;
 &lt;/ref&gt;
 &lt;!--Data reference: NCBI Gene Expression Omnibus: pub-id-type="accession" assigning-authority="NCBI"--&gt;
 &lt;ref id="bib12"&gt;
 &lt;element-citation publication-type="data"&gt;
 &lt;person-group person-group-type="author"&gt;
 &lt;name&gt;
 &lt;surname&gt;Bouveret&lt;/surname&gt;
 &lt;given-names&gt;R&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Waardenberg&lt;/surname&gt;
 &lt;given-names&gt;AJ&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Schonrock&lt;/surname&gt;
 &lt;given-names&gt;N&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Ramialison&lt;/surname&gt;
 &lt;given-names&gt;M&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Doan&lt;/surname&gt;
 &lt;given-names&gt;T&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;de Jong&lt;/surname&gt;
 &lt;given-names&gt;D&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Bondue&lt;/surname&gt;
 &lt;given-names&gt;A&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Kaur&lt;/surname&gt;
 &lt;given-names&gt;G&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Mohamed&lt;/surname&gt;
 &lt;given-names&gt;S&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Fonoudi&lt;/surname&gt;
 &lt;given-names&gt;H&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Chen&lt;/surname&gt;
 &lt;given-names&gt;C&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Wouters&lt;/surname&gt;
 &lt;given-names&gt;M&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Bhattacharya&lt;/surname&gt;
 &lt;given-names&gt;S&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt; Plachta&lt;/surname&gt;
 &lt;given-names&gt;N&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Dunwoodie&lt;/surname&gt;
 &lt;given-names&gt;SL&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Chapman&lt;/surname&gt;
 &lt;given-names&gt;G&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Blanpain&lt;/surname&gt;
 &lt;given-names&gt;C&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Harvey&lt;/surname&gt;
 &lt;given-names&gt;RP&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;/person-group&gt;
 &lt;year iso-8601-date="2015"&gt;2015&lt;/year&gt;
 &lt;data-title&gt;NKX2-5 mutations causative for congenital heart disease retain
 functionality and are directed to hundreds of targets&lt;/data-title&gt;
 &lt;source&gt;NCBI Gene Expression Omnibus&lt;/source&gt;
 &lt;pub-id pub-id-type="accession" assigning-authority="NCBI"
 xlink:href="https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE44902"
 &gt;GSE44902&lt;/pub-id&gt;
 &lt;/element-citation&gt;
 &lt;/ref&gt;
 &lt;!--Data reference: NCBI Nucleotide: pub-id-type="accession" assigning-authority="NCBI" contains version details--&gt;
 &lt;ref id="bib13"&gt;
 &lt;element-citation publication-type="data"&gt;
 &lt;person-group person-group-type="author"&gt;
 &lt;name&gt;
 &lt;surname&gt;Gavrilov&lt;/surname&gt;
 &lt;given-names&gt;S&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Harvey&lt;/surname&gt;
 &lt;given-names&gt;RP&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Papaioannou&lt;/surname&gt;
 &lt;given-names&gt;VE&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;/person-group&gt;
 &lt;year iso-8601-date="2014"&gt;2014&lt;/year&gt;
 &lt;data-title&gt;Mus musculus T-box 2 (Tbx2), mRNA&lt;/data-title&gt;
 &lt;source&gt;NCBI Nucleotide&lt;/source&gt;
 &lt;pub-id pub-id-type="accession" assigning-authority="NCBI"
 xlink:href="http://www.ncbi.nlm.nih.gov/nuccore/120407038"
 &gt;NM_009324&lt;/pub-id&gt;
 &lt;version designator="NM_009324.2"&gt;NM_009324.2&lt;/version&gt;
 &lt;/element-citation&gt;
 &lt;/ref&gt;
 &lt;!--Data reference: NCBI Gene Expression Omnibus (GEO): pub-id-type="accession" assigning-authority="NCBI"--&gt;
 &lt;ref id="bib14"&gt;
 &lt;element-citation publication-type="data"&gt;
 &lt;person-group person-group-type="author"&gt;
 &lt;name&gt;
 &lt;surname&gt;Hoang&lt;/surname&gt;
 &lt;given-names&gt;C&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Swift&lt;/surname&gt;
 &lt;given-names&gt;GH&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Azevedo-Pouly&lt;/surname&gt;
 &lt;given-names&gt;A&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;MacDonald&lt;/surname&gt;
 &lt;given-names&gt;RJ&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;/person-group&gt;
 &lt;year iso-8601-date="2015"&gt;2015&lt;/year&gt;
 &lt;data-title&gt;Effects on the transcriptome of adult mouse pancreas (principally
 acinar cells) by the inactivation of the Ptf1a gene in vivo&lt;/data-title&gt;
 &lt;source&gt;NCBI Gene Expression Omnibus&lt;/source&gt;
 &lt;pub-id pub-id-type="accession" assigning-authority="NCBI"
 xlink:href="http://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE70542"
 &gt;GSE70542&lt;/pub-id&gt;
 &lt;/element-citation&gt;
 &lt;/ref&gt;
 &lt;!--Data reference: NCBI BioProject: author is a collab pub-id-type="accession" assigning-authority="NCBI" example of 3 references with same author/year--&gt;
 &lt;ref id="bib15"&gt;
 &lt;element-citation publication-type="data"&gt;
 &lt;person-group person-group-type="author"&gt;
 &lt;collab&gt;The &lt;italic&gt;Shigella&lt;/italic&gt; Genome Sequencing Consortium&lt;/collab&gt;
 &lt;/person-group&gt;
 &lt;year iso-8601-date="2015"&gt;2015a&lt;/year&gt;
 &lt;data-title&gt;Global Diversity of Shigella Species&lt;/data-title&gt;
 &lt;source&gt;NCBI BioProject&lt;/source&gt;
 &lt;pub-id pub-id-type="accession" assigning-authority="NCBI"
 xlink:href="http://www.ncbi.nlm.nih.gov/bioproject/?term=PRJEB2846"
 &gt;PRJEB2846&lt;/pub-id&gt;
 &lt;/element-citation&gt;
 &lt;/ref&gt;
 &lt;ref id="bib16"&gt;
 &lt;element-citation publication-type="data"&gt;
 &lt;person-group person-group-type="author"&gt;
 &lt;collab&gt;The &lt;italic&gt;Shigella&lt;/italic&gt; Genome Sequencing Consortium&lt;/collab&gt;
 &lt;/person-group&gt;
 &lt;year iso-8601-date="2015"&gt;2015b&lt;/year&gt;
 &lt;data-title&gt;Shigella sonnei and flexneri from around the world&lt;/data-title&gt;
 &lt;source&gt;NCBI BioProject&lt;/source&gt;
 &lt;pub-id pub-id-type="accession" assigning-authority="NCBI"
 xlink:href="http://www.ncbi.nlm.nih.gov/bioproject/204320"
 &gt;PRJEB2460&lt;/pub-id&gt;
 &lt;/element-citation&gt;
 &lt;/ref&gt;
 &lt;ref id="bib17"&gt;
 &lt;element-citation publication-type="data"&gt;
 &lt;person-group person-group-type="author"&gt;
 &lt;collab&gt;The &lt;italic&gt;Shigella&lt;/italic&gt; Genome Sequencing Consortium&lt;/collab&gt;
 &lt;/person-group&gt;
 &lt;year iso-8601-date="2015"&gt;2015c&lt;/year&gt;
 &lt;data-title&gt;Shigella flexneri from around the world&lt;/data-title&gt;
 &lt;source&gt;NCBI BioProject &lt;/source&gt;
 &lt;pub-id pub-id-type="accession" assigning-authority="NCBI"
 xlink:href="http://www.ncbi.nlm.nih.gov/bioproject/?term=PRJEB2542"
 &gt;PRJEB2542&lt;/pub-id&gt;
 &lt;/element-citation&gt;
 &lt;/ref&gt;
 &lt;!--Data reference: JASPAR--&gt;
 &lt;ref id="bib18"&gt;
 &lt;element-citation publication-type="data"&gt;
 &lt;person-group person-group-type="author"&gt;
 &lt;name&gt;
 &lt;surname&gt;Staab&lt;/surname&gt;
 &lt;given-names&gt;TA&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Griffen&lt;/surname&gt;
 &lt;given-names&gt;TC&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Corcoran&lt;/surname&gt;
 &lt;given-names&gt;C&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Evgrafov&lt;/surname&gt;
 &lt;given-names&gt;O&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Knowles&lt;/surname&gt;
 &lt;given-names&gt;JA&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Sieburth&lt;/surname&gt;
 &lt;given-names&gt;D&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;/person-group&gt;
 &lt;year iso-8601-date="2013"&gt;2013&lt;/year&gt;
 &lt;data-title&gt;SKN-1 from the JASPAR CORE database&lt;/data-title&gt;
 &lt;source&gt;JASPAR&lt;/source&gt;
 &lt;pub-id pub-id-type="art-access-id"
 xlink:href="http://jaspar.genereg.net/cgi-bin/jaspar_db.pl"
 &gt;MA0547.1&lt;/pub-id&gt;
 &lt;/element-citation&gt;
 &lt;/ref&gt;
 &lt;!--Data reference: modMine pub-id-type="archive"--&gt;
 &lt;ref id="bib19"&gt;
 &lt;element-citation publication-type="data"&gt;
 &lt;person-group person-group-type="author"&gt;
 &lt;name&gt;
 &lt;surname&gt;Zhong&lt;/surname&gt;
 &lt;given-names&gt;M&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Snyder&lt;/surname&gt;
 &lt;given-names&gt;M&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Slightam&lt;/surname&gt;
 &lt;given-names&gt;C&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Kim&lt;/surname&gt;
 &lt;given-names&gt;S&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Murray&lt;/surname&gt;
 &lt;given-names&gt;J&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Waterston&lt;/surname&gt;
 &lt;given-names&gt;R&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Gerstein&lt;/surname&gt;
 &lt;given-names&gt;M&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Niu&lt;/surname&gt;
 &lt;given-names&gt;W&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Janette&lt;/surname&gt;
 &lt;given-names&gt;J&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Raha&lt;/surname&gt;
 &lt;given-names&gt;D&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Agarwal&lt;/surname&gt;
 &lt;given-names&gt;A&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Reinke&lt;/surname&gt;
 &lt;given-names&gt;V&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Sarov&lt;/surname&gt;
 &lt;given-names&gt;M&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;name&gt;
 &lt;surname&gt;Hyman&lt;/surname&gt;
 &lt;given-names&gt;A&lt;/given-names&gt;
 &lt;/name&gt;
 &lt;/person-group&gt;
 &lt;year iso-8601-date="2013"&gt;2013&lt;/year&gt;
 &lt;data-title&gt;ChIP-Seq Identification of C. elegans TF Binding Sites&lt;/data-title&gt;
 &lt;source&gt;modMine&lt;/source&gt;
 &lt;pub-id pub-id-type="archive" xlink:href="http://intermine.modencode.org/release-33/report.do?id=77000379"&gt;modENCODE_3369&lt;/pub-id&gt;
 &lt;/element-citation&gt;
 &lt;/ref&gt;
</pre>
<pre></pre>