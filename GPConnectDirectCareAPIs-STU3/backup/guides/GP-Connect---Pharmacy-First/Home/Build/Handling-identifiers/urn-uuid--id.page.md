## {{page-title}}

ITK3 uses `urn:uuid:[id]` to identify resources within the body of the message. Therefore, this specification has used the same, and this is what receivers are expecting to be within the payload.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: Please ensure that identifiers are provided in this way - from a provider perspective, if they have built Access Record: Structured, then they will need to modify the <code>id</code> and <code>identifier</code> elements accordingly to support Update Record.
</div>

---