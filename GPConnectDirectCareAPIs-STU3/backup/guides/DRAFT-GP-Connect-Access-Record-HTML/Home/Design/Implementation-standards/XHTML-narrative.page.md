## {{page-title}}

As outlined in the '[Narrative](https://www.hl7.org/fhir/narrative.html)' section of the FHIR® standard:

> The XHTML content MUST NOT contain a head, a body element, external stylesheet references, deprecated elements, scripts, forms, base/link/xlink, frames, iframes, objects or event related attributes (for example, onClick). This is to ensure that the content of the narrative is contained within the resource and that there is no active content. Such content would introduce security issues and potentially safety issues with regard to extracting text from the XHTML.

Note that the XHTML is contained in general XML so there is no support for HTML entities like `&nbsp;` or `&copy;`. Unicode characters MUST be used instead. Unicode `&#160;` substitutes for `&nbsp;`.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
        <i class="fa fa-exclamation-triangle"></i> <b>Important:</b> The content <b>MUST NOT</b> contain any platform-specific escape or formatting characters such as <code>\r\n</code>, as these may cause inconsistent rendering within consumer applications, with potential impacts on clinical safety.
</div>