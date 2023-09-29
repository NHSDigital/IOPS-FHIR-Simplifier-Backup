## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: In FHIR, the terminology to update a payload is known as a <code>replacement</code>.
</div>

The GP Connect Update Record capability allows for the updating of a previously sent payload. 

This replacement is at a whole payload level, in that the original payload is replaced by a new one and the old payload is only kept for audit purposes. 

A sender may choose to send a new replacement payload for several reasons, for example:

- the original payload contained an error, identified after the payload was sent
- the sender has more up-to-date or complete information - for example, the original is correct but further information is now available to make the payload more complete or detailed
- receivers of updated versions of payloads **MUST** process the updated payload and archive the previous one

---