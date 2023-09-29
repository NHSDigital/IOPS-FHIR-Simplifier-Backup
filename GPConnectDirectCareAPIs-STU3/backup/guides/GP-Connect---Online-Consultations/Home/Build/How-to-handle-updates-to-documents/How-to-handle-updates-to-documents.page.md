## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: In FHIR, the terminology to update a document is known as a <code>replacement</code>.
</div>

The Send Document capability allows for the updating of a previously sent document. 

This replacement is at a whole document level, in that the original document is replaced by a new one and the old document is only kept for audit purposes. 

A sender may choose to send a new replacement document for several reasons, for example:

- the original document contained an error, identified after the document was sent
- the sender has more up-to-date or complete information - for example, the original is correct but further information is now available to make the document more complete or detailed
- receivers of updated versions of documents **MUST** process the updated document and archive the previous one

---