---
ID: 486
post_title: General recommendations
author: seligym@gmail.com
post_date: 2016-03-10 16:09:54
post_excerpt: ""
layout: page
permalink: >
  http://jats4r.org/general-recommendations/
published: true
spacious_page_layout:
  - default_layout
---
<h1 class="rec-heading">General recommendations</h1>
<span class="status">Status: <span style="color: #ff9900;"><strong>DRAFT</strong></span></span>
<h2>Context</h2>
JATS articles as XML documents.
<h2>Description</h2>
These recommendations apply to an article’s XML as a whole; i.e., they are best practices for setting up a JATS article XML document.

<strong>N.B.</strong> These recommendations are applicable to NISO JATS Z39.96-2012, version 1.0 of the tagset or later.
<h2>Which JATS DTD?</h2>
When recommendations are applicable to only a specific version of JATS, this will be indicated. The validator will not produce warnings or failure messages when testing those recommendations against a document that conforms to some other version.

The tool and recommendations are designed to work for both Publishing (Blue) and Archiving (Green) schemas. When recommendations only apply to one of the schemas, that will be indicated in the recommendations document, and the validator will not produce error or warning messages if the article declares itself as conforming to the other.

The JATS Article Authoring schema was designed to allow an author to capture original work in XML. Articles in this schema are in the publication process and are not meant for reuse. While some of the JATS4R guidelines may apply to articles in the Authoring model, these recommendations are not intended for use at that stage.
<h2>Recommendations</h2>
<ol>
	<li><strong>XML Structure</strong>. All JATS4R-compliant article XML files must self-identify which version of JATS they conform to, by unambiguously referencing one JATS schema. The JATS schemas are available in three languages, and one (and only one) of these should be referenced. Those three languages are:
<ul style="margin-top: 15px;">
	<li>DTD</li>
	<li>Relax-NG</li>
	<li>W3C Schema (XSD)</li>
</ul>
There are three different methods that an article XML file can use to refer to its schema. These are given in the following table, which also indicates which method is used for each language.
<table>
<tbody>
<tr>
<td style="vertical-align: bottom;" rowspan="2"><b>Reference method</b></td>
<td colspan="3"><b>Schema language</b></td>
</tr>
<tr>
<td><b>DTD</b></td>
<td><b>W3C XSD</b></td>
<td><b>Relax-NG</b></td>
</tr>
<tr>
<td>DOCTYPE declaration</td>
<td>✓</td>
<td></td>
<td></td>
</tr>
<tr>
<td>@noNamespaceSchemaLocation attribute</td>
<td></td>
<td>✓</td>
<td></td>
</tr>
<tr>
<td>&lt;?xml-model?&gt; processing instruction</td>
<td>✓</td>
<td>✓</td>
<td>✓</td>
</tr>
</tbody>
</table>
</li>
	<li><strong>DOCTYPE declarations</strong>. The most common JATS articles use a DOCTYPE declaration to reference the specific version of the JATS DTD. When using a DOCTYPE declaration, the document must use PUBLIC form, with the public identifier, and the complete, absolute URL of the system identifier.For example:
<pre><code class='language-markup'>&lt;!DOCTYPE article
 PUBLIC "-//NLM//DTD JATS (Z39.96) Journal Publishing DTD v1.1 20151215//EN"
 "http://jats.nlm.nih.gov/publishing/1.1/JATS-journalpublishing1.dtd"&gt;
&lt;article dtd-version="1.1" 
 xmlns:xlink="http://www.w3.org/1999/xlink"
 xmlns:mml="http://www.w3.org/1998/Math/MathML"&gt;
 ...
&lt;/article&gt;</code></pre>
</li>
	<li><strong>@noNamespaceSchemaLocation attribute</strong>.For example:
<pre>&lt;article dtd-version="1.1" 
 xmlns:xlink="http://www.w3.org/1999/xlink"
 xmlns:mml="http://www.w3.org/1998/Math/MathML"
 xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
 xsi:noNamespaceSchemaLocation=
 "http://jats.nlm.nih.gov/publishing/1.1/xsd/JATS-journalpublishing1.xsd"&gt;
 ...
&lt;/article&gt;
</pre>
</li>
	<li><strong>xml-model processing instruction</strong>. An article can use the &lt;?xml-model?&gt; processing instruction (see <a href="http://www.w3.org/XML/2010/01/xml-model/" target="_blank">the specification</a>), to refer to <i><span style="font-weight: 400;">any</span></i> of the three languages of JATS. When using the &lt;?xml-model?&gt; processing instruction, place it before the root element. The processing instruction MUST have an @href pseudo-attribute, and the content of this pseudo-attribute must be the absolute, complete URL of the schema.For example, the following is an example of using the processing instruction to refer to the DTD:
<pre><code class='language-markup'>&lt;?xml-model type="application/xml-dtd"
 href="http://jats.nlm.nih.gov/publishing/1.1/JATS-journalpublishing1.dtd"?&gt;
&lt;article dtd-version="1.1" 
 xmlns:xlink="http://www.w3.org/1999/xlink"
 xmlns:mml="http://www.w3.org/1998/Math/MathML"&gt;
 ...
&lt;/article&gt;</code>
</pre>
The following is an example of using it to reference the Relax-NG version of JATS:
<pre>&lt;?xml-model schematypens="http://relaxng.org/ns/structure/1.0"
 href="http://jats.nlm.nih.gov/publishing/1.1/rng/JATS-journalpublishing1.rng"?&gt;
&lt;article dtd-version="1.1" 
 xmlns:xlink="http://www.w3.org/1999/xlink"
 xmlns:mml="http://www.w3.org/1998/Math/MathML"&gt;
 ...
</pre>
And finally, to reference the W3C XSD version:
<pre>&lt;?xml-model schematypens="http://www.w3.org/2001/XMLSchema"
 href="http://jats.nlm.nih.gov/publishing/1.1/xsd/JATS-journalpublishing1.xsd"?&gt;
&lt;article dtd-version="1.1" 
 xmlns:xlink="http://www.w3.org/1999/xlink"
 xmlns:mml="http://www.w3.org/1998/Math/MathML"&gt;
 ...
&lt;/article&gt;
</pre>
</li>
	<li><strong>Character encoding</strong>. All JATS XML documents should be encoded either as UTF-8 or UTF-16.Note: A byte order mark (BOM)
<ul style="margin-top: 15px;">
	<li>May be present if the encoding is UTF-8</li>
	<li>Must be present if the encoding is UTF-16&lt;</li>
</ul>
Also note that US-ASCII, which is commonly used, is a subset of UTF-8, so files that are restricted to the US-ASCII are perfectly fine, but if an XML declaration is given, the encoding should be specified as “utf-8”. [Validator tool result: Error]</li>
	<li><strong>Character entity references.</strong> Do not use named character entity references to represent special characters (see rationale, below). Instead, use either a non-escaped form of the character or a numeric character reference.<i>Rationale</i>: The JATS DTDs define a large set of character entity references (CERs), that they inherit from MathML. (See  MathML <a href="http://www.w3.org/TR/MathML2/chapter6.html">Chapter 6. Characters Entities and Fonts</a> for a list.)  These appear in XML document as, for example, “&amp;copy;”, and get translated by the XML parser into Unicode code points. In order to correctly parse XML files that use CERs, a tool would be required to fetch and parse the entire DTD. Because configuring a system to correctly fetch a DTD, either from the Internet, or from an internally cached version, can be quite burdensome, JATS4R recommends that instance documents <i>do not use CERs</i>.Note that this do not include the five “built-in” XML character entities <span style="font-weight: 400;"> “&amp;lt;”, “&amp;gt;”, “&amp;apos;”, “&amp;quot;” and “&amp;amp;”</span>. All XML-compliant parsers are able to expand these without reference to the DTDs.So, for example, the following copyright-statement would not be JATS4R-compliant:&lt;copyright-statement&gt;&amp;copy; 2014 Surname et al.&lt;/copyright-statement&gt;Instead, the copyright symbol should be included either directly in the document in non-escaped form (preferred):&lt;copyright-statement&gt;© 2014 Surname et al.&lt;/copyright-statement&gt;or, as a numeric character reference:&lt;copyright-statement&gt;© 2014 Surname et al.&lt;/copyright-statement&gt;</li>
	<li>@dtd-version attribute. Use the @dtd-version attribute on &lt;article&gt; with the value that is FIXED (or default) in the schema that is referenced in the DOCTYPE (for DTD), @schemaLocation or @noNamespaceSchemaLocation attribute (for XSD), or processing instruction (for RNG). [Validator tool result: Warning if it’s not there]</li>
</ol>

<pre><code class="language-markup">p { color: red }</code></pre>