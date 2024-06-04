## {{page-title}}

<p>The result of a query for referral details <strong>MUST</strong> return a <code>List</code> containing references to all <code>ReferralRequest</code> resources that are returned.</p>

<p>The <code>List</code> <strong>MUST</strong> be populated in line with the guidance on <code>List</code> resources.</p>

<p>If the <code>List</code> is empty, then an empty <code>List</code> <strong>MUST</strong> be returned with an <code>emptyReason</code> with the value <code>no-content-recorded</code>.</p>