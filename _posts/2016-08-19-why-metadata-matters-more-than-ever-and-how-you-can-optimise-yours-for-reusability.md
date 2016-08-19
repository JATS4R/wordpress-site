---
ID: 727
post_title: >
  Why Metadata Matters More than Ever (and
  how you can optimise yours for
  reusability)
author: seligym@gmail.com
post_date: 2016-08-19 14:09:20
post_excerpt: ""
layout: post
permalink: >
  http://jats4r.org/why-metadata-matters-more-than-ever-and-how-you-can-optimise-yours-for-reusability/
published: true
spacious_page_layout:
  - default_layout
---
<span class="drop"><a href="http://jats4r.org/wp-content/uploads/2016/08/stamp-e1471615950141.png" rel="attachment wp-att-728"><img class="alignleft size-medium wp-image-728" src="http://jats4r.org/wp-content/uploads/2016/08/stamp-300x284.png" alt="Good XML metadata is required to ensure discovery, exchange, and reusability of journal articles" width="300" height="284" /></a><br>W</span>hy is journal article metadata so darned sexy? To be clear, by ‘metadata’ we mean not only the actual metadata itself (the collective information about an article), but also the representation of that metadata in the <a href="http://jats.nlm.nih.gov">JATS XML standard</a>. As if this weren’t exciting enough, the main reason why metadata is increasingly a <a href="https://www.sspnet.org/?s=metadata">hot topic of conversation</a> in scholarly publishing is because in real and practical ways it is an article’s passport to key destinations in the scholarly publishing universe. The quality of XML metadata can mean the difference between an article traveling wherever it needs to and something closer to a ‘stay-cation’ at home. In this article we’ll talk about why XML metadata matters more than ever today, and what you can do to optimise yours for dissemination, discovery and reuse.

Consider the primary objective of a journal article, which is to have its contents disseminated as widely as possible so that it can be used by as many people in as many ways as possible, ultimately serving the larger goal of advancing science and humanities research.

To accomplish this objective, especially in light of the <a href="http://www.ruor.uottawa.ca/bitstream/10393/19577/2/Jinha_Arif_2010_Article_50_million.pdf">titanic volume of journal articles</a> churned out daily, an article has to <a href="http://jats4r.org/have-content-will-travel-xml-and-the-road-to-article-discoverability/">travel many places</a>: in and out of peer review systems, to the publisher’s website, to aggregators, digital catalogs, search engine return pages, databases, and discovery platforms, to partner publishers or societies, repositories, archives, and so on. And just as passports for humans provide authoritative assertions about our identities to the gatekeepers who permit our passage, article metadata provides the gatekeepers of key article destinations with assertions about the provenance, authorship, ownership, access, funding, and relevance of an article, all of which are useful (if not specifically required) for its admission to those destinations.

Humans are the end-users we typically have in mind when we publish articles. People need metadata to help them decide whether to invest the time to read (and cite) content, to properly store, organise and curate it, or to decide to fund more of it.

But in scholarly publishing today, no human reads an article before it is read by a machine. Whether it is a researcher looking at content on the journal’s website, a librarian cataloging an article for their users, or a funder reviewing research, the content in question is served to the human after a machine (or series of machines) has processed that content’s metadata. And there is no shortage of metadata to process: as people find ever more interesting and inventive ways to use content, the systems and tools required to do the work will require more and more metadata to understand and access the content they are tasked with processing. Furthermore, as the need to <a href="https://www.sspnet.org/?s=standard">standardise content</a> for improved interoperability increases, so does the need for persistent identifiers and other new forms of metadata that all must be captured within an article’s XML.

It is clear that if we want to achieve our objectives for journal content, we need to satisfy our machine readers with machine-friendly metadata. But what does ‘machine-friendly’ mean?

Unlike humans, who may not love but can tolerate a few quirks and a little ambiguity in metadata, machines are not flexible readers. Machine systems function effectively and efficiently with data that is accurate, consistent, detailed, and predictable. Sloppy, incomplete, or inconsistent metadata may seriously limit (if not prevent) an article’s potential for wide dissemination, discovery, exchange, and reuse by machine systems. If you are not sure where to begin to make your metadata machine-worthy, fret not! Below are the three main rules to follow for creating quality machine-friendly metadata.
<h2>1. Be consistent</h2>
An important rule for all quality XML tagging is consistency, and this applies to both metadata and full-text documents. Although JATS is an <a href="http://www.niso.org/apps/group_public/project/details.php?project_id=93">XML standard</a> that is (almost) ubiquitously used in scholarly publishing today, it is also a loose standard, which means that there may be many ways to tag the same item and still be valid. The important thing is to choose a consistent way to tag a given item within an article and across articles and volumes.

For example, if you have decided that your organization will follow the JATS tag library’s <a href="http://jats.nlm.nih.gov/publishing/tag-library/1.1/element/aff.html">stated best practice for tagging authors and affiliations</a>, then stick to that and do not allow your way to stray to any other model, however valid and reasonable it may be. If you have decided on a particular ID syntax for all your elements with IDs, then stick to that. If you change how you (or a vendor creating XML on your behalf) encode a particular item in XML then make it a conscious, thoughtful decision based on what is best for your organization and the content it provides.
<h2>2. Be explicit</h2>
To a machine, <a href="http://jats4r.org/have-content-will-travel-xml-and-the-road-to-article-discoverability/#text-blob">text on its own is just a meaningless blob</a>. XML makes content accessible to machines, so the more explicit (detailed and specific) the XML, the more ways a machine system has to interact with it and the more possibilities there are for extracting and using components for various purposes. The key is to be explicit without sacrificing accuracy or consistency.

For example, an affiliation can be tagged this way:
<pre>&lt;aff&gt;Nunavut Arctic College, Repulse Bay, Nunavut X0A 0H0, Canada.&lt;/aff&gt;
</pre>
But depending on whether it is possible to accurately and consistently tag components of the affiliation above, you might have
<pre>&lt;aff id=”aff1”&gt;Nunavut Arctic College, &lt;city&gt;Repulse Bay&lt;/city&gt;, &lt;state&gt;Nunavut&lt;/state&gt; &lt;postal-code&gt;X0A 0H0&lt;/postal-code&gt;, &lt;country&gt;Canada&lt;/country&gt;.&lt;/aff&gt;
</pre>
Or even
<pre>&lt;aff id=”aff1”&gt;&lt;institution-wrap&gt;&lt;institution content-type=”university”&gt;Nunavut Arctic College&lt;/institution&gt;&lt;institution-id id-type=”ringgold”&gt;1931&lt;/institution-id&gt;&lt;/institution-wrap&gt;, &lt;city&gt;Repulse Bay&lt;/city&gt;, &lt;state&gt;Nunavut&lt;/state&gt; &lt;postal-code&gt;X0A 0H0&lt;/postal-code&gt;, &lt;country&gt;Canada&lt;/country&gt;.&lt;/aff&gt;
</pre>
<h2>3. Follow best practices</h2>
This is similar to rule Number One (be consistent), but it means trying to be consistent not only within our own content, but with the content of others in scholarly publishing as well.
Whether we work for a publisher, vendor, compositor, library, or archive, we all benefit from following common XML tagging practices. For example, a publisher may own and control its own website technology, but ultimately its articles are processed by many (if not all) of the same systems that make up the current scholarly publishing infrastructure, such as <a href="http://www.crossref.org/">CrossRef</a>, <a href="http://www.ncbi.nlm.nih.gov/pmc/">PubMed</a>, <a href="http://orcid.org/">ORCID</a>, and <a href="https://scholar.google.ca/intl/en/scholar/about.html">Google Scholar</a>, to name a few. If we all follow the same tagging practices, then the machine systems we collectively use can be programmed to process our content much more efficiently and effectively. Here are some ways to follow common tagging practices:

Look at the <a href="http://jats.nlm.nih.gov/publishing/tag-library/1.1/">JATS tag library documentation</a>. The JATS tag library often indicates common tagging practices, which is a good place to start if you want to tag in ways that are similar to others.

<a href="http://jats.nlm.nih.gov/publishing/tag-library/1.1/">Follow JATS4R</a>. ‘Common’ practice does not mean ‘best’ practice, and although the JATS tag library mentions one or two best practices, it is really not its purview. However, it is the mandate of JATS4R to develop and recommend best practices for tagging content that is machine friendly. Follow or become involved with JATS4R here: <a href="http://jats.nlm.nih.gov/publishing/tag-library/1.1/">http://jats4r.org/how-to-participate/</a>
Talk to other publishers, to see how they tag things. Better yet, ask them to come along to the next JATS4R call.
<p style="font-size: 90%;"><em>By Mary Seligy, on behalf of JATS4R. Mary is currently a business analyst at <a href="http://cdnsciencepub.com">Canadian Science Publishing</a>.
If you would like to contribute an article to the JATS4R XML Learning Centre or have a suggestion, please email <a href="mailto:jats4r@gmail.com">jats4r@gmail.com</a></em></p>