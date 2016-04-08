---
ID: 48
post_title: XML FAQs
author: seligym@gmail.com
post_date: 2015-12-02 19:00:29
post_excerpt: ""
layout: page
permalink: http://jats4r.org/xml-faq/
published: true
spacious_page_layout:
  - no_sidebar_content_centered
---
<h1>Some frequently asked questions about XML</h1>
The following are some general questions we've been asked about XML and XML-related technologies.

If you'd like to ask a question and have it answered here, please post a question on the <a href="https://groups.google.com/forum/#!forum/jats4r">JATS4R mail list</a>. We are looking for any question, no matter the technical level. Remember: if you have a question, chances are someone else does too!

<hr />

<h3>Q: What is XML?</h3>
<span class="faq">A:</span> <a href="https://en.wikipedia.org/wiki/XML" target="_blank">Wikipedia defines XML</a> (eXtensible Markup Language) as<i> </i>a markup language (similar to HTML) that defines a set of rules for encoding documents in a format which is both human-readable and machine-readable. It is defined by the <a href="https://www.w3.org/TR/xml/" target="_blank">W3C's XML 1.0 Specification</a> and by several other related specifications, all of which are free open standards. The design goal of XML is to emphasize simplicity, generality and usability across the Internet, and it is a textual data format with strong support via Unicode for different human languages.

XML essentially consists of elements and attributes, which are simply containers for information (elements) and values that describe what's in the containers or what they are for (attributes). Since the design of XML allows any user to create their own elements and attributes, most XML documents contain a reference to a schema (also known as an XML-constraining document), which is basically a dictionary of the elements and attributes that are allowed in the document and the rules for how those elements and attributes may be applied. A DTD is an example of such a schema.  For more illustrative information about what XML is, and its role in scholarly content (and its discovery), see <a href="http://jats4r.org/have-content-will-travel-xml-and-the-road-to-article-discoverability/">this article in JATS4R's XML topics pages.</a>
<h3>Q: Why should we use XML?</h3>
<span class="faq">A: </span>XML is an excellent, time-tested format for representing and distributing literature such as journal articles in an interoperable, machine-readable way.
<h3>Q: What’s the difference between a DTD and a schema? What are they used for?</h3>
<span class="faq">A:</span> “Schema” is a general term used to describe any specification of an XML document’s data model, semantics, or constraints. To put this in plain language, a schema is basically a dictionary that defines the elements and attributes that are allowed in a given XML document and the rules for how those elements and attributes may be applied and organized within the document. Sometimes a schema is referred to informally as an XML-constraining document, because it constrains an XML document's elements and attributes according to the definitions and rules within the schema. The word 'schema' can also be used to mean the language in which the schema document is written, e.g., "DTD language".

DTD stands for “Document Type Definition”, and it is only one of several different types of schema (or schema language). Other kinds of schema types used with XML documents are Relax NG (sometimes pronounced “relaxing”, and abbreviated RNG), W3C Schema Definition language (XSD), and Schematron.

<a href="http://www.niso.org/workrooms/journalmarkup" target="_blank">JATS</a> is a standard set of elements and attributes (with some rules about how these may be applied and arranged), <a href="http://jats.nlm.nih.gov/files.html" target="_blank">which is available to users in three schema formats</a>: DTD, Relax NG, and XSD. It is up to the user which schema they choose to constrain their XML documents, but most choose the DTD form, for the reasons described above.
<h3>Q: Why is JSON always being talked about now? Will it replace XML?</h3>
<span class="faq">A: </span>JSON (pronounced like the name “Jason”) stands for “JavaScript Object Notation”. As the name implies, it originated in the JavaScript language. Compared to XML, it is an extremely simple format, and many believe that that is one of the main reasons for its success. JSON documents tend to be highly structured, and are good for storing data that is highly structured, such as tables, spreadsheets, and small databases. Journal articles, however, are often described as “semi-structured”, because they are a mixture of tabular, machine readable data (publisher, contributors, dates, etc.) and free-form mixed-content (text and markup).  Since JSON has no native support for “mixed content”, it is not a good fit for semi-structured data such as journal articles.
<h3>Q: What’s the difference between JSON and XML?</h3>
<span class="faq">A: </span>There are many differences, but the one of the most prominent is that whereas JSON is simple, XML is complex. JSON’s complete specification fits on just two or three printed pages, while XML’s is about twenty times the length. Simplicity was considered so important that the author of the specification, Douglas Crockford, even <a href="https://plus.google.com/+DouglasCrockfordEsq/posts/RK8qyGVaGSr">removed the ability to add comments</a>.
So, JSON has none of the “heavy baggage” of XML, but that also means that it has none of the extra features, such as those provided by DTDs: ability to define the schema of the documents, internal entities, which can be used like “macros” for long snippets of text, or external entities, which can be used as an inclusion mechanism -- such as a master book XML that includes separate files for each chapter. (Many would say that that’s a good thing, however: that those features should be defined by higher-level standards.)