## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Important</strong>: This element <b>MUST</b> be used to identify the type of document that has been received.
    <br />
    <br />
    The MESH workflow ID or the <code>LocalExtension</code> value provided in the <code>Extension-ITK-MessageHandling-2</code> resource <b>MUST NOT</b> be used to identify the document.
</div>

A SNOMED code must be used when populating this element.

An example SNOMED code could be (but not limited to):

[149951000000107  | Patient information received using general practice online consultation system (finding)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=149951000000107&edition=uk-edition)

<h5><ins>Example</ins></h5>

```xml
<coding>
    <system value="http://snomed.info/sct" />
    <code value="149951000000107" />
    <display value="Patient information received using general practice online consultation system (finding)" />
</coding>
```

---