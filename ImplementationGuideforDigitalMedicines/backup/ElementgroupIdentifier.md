## Element: `groupIdentifier` <span class="mro-circle optional" title="Optional"></span>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6">
   <strong>Recommendation</strong>: not implemented as part of an MVP.
   <br />
   <br />
   The ability to group medication requests from the same requester, and in additional for the same patient may add business benefit in an enhanced implementation. Such medication requests may or may not be contained within the same interaction <code>Bundle</code>. 
   <br />
   <br />
   For example, the FHIR interface for the Electronic Prescription Service uses the <code>groupIdentifier</code> to group medication requests for the same patient, prescribed at the same time, contained within a single <code>Bundle</code>. 
</div>


Where Bundles are not used, or where requests are split across Bundles then the `groupIdentifier` provides the means to link requests by the same prescriber for the same patient.

---