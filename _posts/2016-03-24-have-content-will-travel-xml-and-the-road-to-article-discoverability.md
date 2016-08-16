---
ID: 521
post_title: 'Have Content, Will Travel: XML and the road to article discovery'
author: JATS4R
post_date: 2016-03-24 12:28:29
post_excerpt: ""
layout: post
permalink: >
  http://jats4r.org/have-content-will-travel-xml-and-the-road-to-article-discoverability/
published: true
spacious_page_layout:
  - right_sidebar
---
<a href="http://jats4r.org/wp-content/uploads/2016/03/xml.jpg" rel="attachment wp-att-497"><img class="wp-image-497 alignleft" src="http://jats4r.org/wp-content/uploads/2016/03/xml.jpg" alt="xml" width="228" height="228" /></a>

<span class="drop">O</span>nce upon a time (a mere decade or two ago), accepted research articles made their way from author to audience by a singular and predictable path.

First, a paper went through the rigorous process of copy-editing. Page composition came next, and after all i’s had been dotted and t’s crossed, the article was sent to the printing press for reproduction and binding into its issue. Eventually, in its sole incarnation as printed matter, the article arrived at its final destination, the Library Shelf.

Discovery of the article was the chance result of librarians perusing printed catalogs of new content, enterprising authors distributing their reprints to colleagues at conferences, or diligent researchers plumbing the depths of the library stacks for relevant references.

Today, an article no longer follows one simple path to its audience, but instead exists in a kind of journal article ‘<a href="http://en.wikipedia.org/wiki/Multiverse" target="_blank">multiverse</a>’, in which an article can exist simultaneously in a multitude of forms that can travel to myriad destinations.

An article can exist as an online .PDF file (for downloading and printing), in full-text form on web pages that can be browsed on a reader’s laptop or desktop computer, or as an optimized web file for viewing on mobile devices. And while the article is on display in its various forms, it can also silently persist as a stored data file, ready for access by various machines for various applications. Finally, an article may still be found (though increasingly less often) in print, on the trusty (though perhaps dusty) Library Shelf.

And in terms of discovery, not even the sky may be the limit. Certainly an article can be found by readers using the search box or the content tree (such as a list-of-issues page) directly on the publisher’s website. But often it is discovered through search engines (like <a href="http://scholar.google.ca/" target="_blank">Google Scholar</a>), on content aggregator or digital repository websites (such as <a href="http://www.ncbi.nlm.nih.gov/pmc/" target="_blank">PubMed Central)</a>, by<a href="http://nrcresearchpress.com/page/help/topics/alerts/rss" target="_blank"> RSS feeds</a> served up on feed readers, by email alerts delivered upon the article’s publication, and via links to various <a href="http://twitter.com/cdnsciencepub" target="_blank">social media channels.</a>

It’s tempting to conclude that the journal article multiverse is simply the result of computerization. But computers don’t understand human languages directly; an article that is simply a text file with some images is pretty much meaningless.

Computers need indicators built into an article so that they can recognize that a collection of text and images is in fact a journal article, and that the article contains objects such as a title, author names, figures, body text, tables, and references. Once these parts are identified, computerized systems can then convert the content to display on web pages, store it in a database that can be used by other systems, send it out as an <a href="http://nrcresearchpress.com/page/help/topics/alerts/rss" target="_blank">RSS feed</a>, or share it with indexers and aggregators.

In modern scholarly publishing systems, a programming language called XML is used to enable computerized systems to identify journal articles and the objects they contain. XML stands for eXtensible Mark-up Language, and it basically consists of a set of labeled (or tagged) containers for the various parts of scholarly article and journal content.  Both humans and computers can understand XML, and once applied to an article’s content, that content can enter its multiverse and travel anywhere it needs to go.

<span id="text-blob">Consider this:</span>

<a href="http://jats4r.org/wp-content/uploads/2016/03/greek_text.png" rel="attachment wp-att-502"><img class="alignnone wp-image-502" src="http://jats4r.org/wp-content/uploads/2016/03/greek_text-300x91.png" alt="greek_text" width="343" height="104" /></a>

To any human, this would literally be <a href="http://en.wikipedia.org/wiki/Odyssey" target="_blank">ancient Greek</a>. To a computer, it’s a meaningless blob. Nothing about it tells a computer what it is, never mind how to display it, store it, or share it.

But what if we were to mark up this content with some XML, like this:

<a href="http://jats4r.org/wp-content/uploads/2016/03/greek_text_XML_mark_up.png" rel="attachment wp-att-503"><img class="alignnone wp-image-503" src="http://jats4r.org/wp-content/uploads/2016/03/greek_text_XML_mark_up-300x140.png" alt="greek_text_XML_mark_up" width="533" height="249" /></a>

Now the context becomes clear to humans, and computers have some indicators of the content’s parts. But both the blessing and the curse of XML is that you can make up your own tags. That’s why the final piece of this puzzle is something called a DTD (<a href="http://en.wikipedia.org/wiki/Document_Type_Definition" target="_blank">document type definition</a>), which is basically just a dictionary of tag names being used and some rules about how they can be applied. With this final piece of information, a computer would have the means to identify, display, share, distribute, and store the various components of the content shown above in a way that is meaningful and discoverable.

In scholarly publishing, it is critical for publishers, aggregators, indexers, scholarly web platforms, and digital repositories to agree to use a standard of set of XML tags and their definitions and to apply it as consistently as possible to the same parts of article content. Without this, the potential to share and distribute content via XML across systems would lost.

Fortunately, such a standard of XML exists in scholarly publishing, which is the standard we all know and use: <a href="http://jats.nlm.nih.gov/index.html">JATS</a>. Until recently, JATS was called the NLM DTD, because it was created by the <a href="http://www.nlm.nih.gov/" target="_blank">National Library of Medicine</a> (NLM) at Bethesda, MD. As of 2012, the NLM DTD became a <a href="http://www.niso.org/workrooms/journalmarkup">NISO standard</a>, and is now referred to as the JATS DTD (Journal Authoring Tag Suite DTD).

One of the goals of JATS4R is to help scholarly content creators make XML that improves everyone’s experience with, and discovery of, our journal article content. By adopting some common best tagging practices in JATS, we have the ability to not only efficiently deliver our content wherever it needs to go now, but to prepare it for travel to parts as-yet unknown.
<p style="font-size: 90%;"><em>This article is adapted from its original form, which was written by Mary Seligy for, and published by, <a href="http://cdnsciencepub.com">Canadian Science Publishing</a> on its CSP Blog. Adapted and reused with the permission of CSP.</em></p>
&nbsp;