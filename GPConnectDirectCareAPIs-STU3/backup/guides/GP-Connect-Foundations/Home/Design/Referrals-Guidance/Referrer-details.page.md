## {{page-title}}
The provider <strong>MUST</strong> populate the <code>requester</code> with the practitioner who recorded the referral, if available.
This may be a clinician or a member of the administrative staff.
The role, organisation and contact details for the referrer <strong>MUST</strong> be included with the bundled resource as available.

If the organisation referenced from the bundled <code>practitioner</code> resource is not the GP practice responsible for the referral, then the <code>onBehalfOf</code> element <strong>SHOULD</strong> reference to an <code>organization</code> resource for the GP practice responsible for the referral.