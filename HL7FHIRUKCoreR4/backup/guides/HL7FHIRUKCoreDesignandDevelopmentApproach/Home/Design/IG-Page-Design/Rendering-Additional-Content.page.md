## {{page-title}}

Where guidance has been added in another IG, such as the glossary, this can be rendered in an IG using the Simpifier { {render: command, which can work across projects and organisations.

For example, the Glossary is rendered via:
~~~~html
{ {render:hl7fhirukcorer4/index-duplicate-49}}
~~~~

<div markdown="span" class="alert alert-warning" role="alert">
<h4><i class="fa fa-info-circle"></i> Important</h4>
Ensure that you check that Simplifier commands, such as FQL or pagelink / tree / xml / json / render, are processed correctly by the rendered page.
</div>

---

Images can be rendered using the same { {render:}} command, and SHALL be within a div with id beginning "renderParent", and SHALL contains a title attirbute which will be used for the alt text.

~~~~html
<div id="renderParent" title="The logos of organisations involved in developing and implementing UK Core">
{ {render:ukcorelogos2023}}
</div>
~~~~

---