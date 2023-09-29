## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Avoid if using MESH"></span> Optional


<h5><ins>Guidance</ins></h5>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: This only applies if your organisation is using MESH for message routing. If your organisation is using FHIR, then this element must be populated. Guidance on how to populate this will be provided in a future version of this implementation guide.
</div>

This value **DOES NOT** need to be present. The Send Document capability currently relies on MESH message routing to be used to route the message to the registered GP practice using a citizen's:

- NHS Number
- date of birth
- surname

---