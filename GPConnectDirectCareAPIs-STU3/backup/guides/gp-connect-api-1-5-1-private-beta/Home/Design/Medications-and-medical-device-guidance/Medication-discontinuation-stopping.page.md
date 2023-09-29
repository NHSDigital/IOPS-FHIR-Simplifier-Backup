## {{page-title}}

Where a medication/medical device is stopped or discontinued then the status of the authorisation <strong>MUST</strong> be changed to ‘stopped’ and a textual stop reason provided via <code class="highlighter-rouge">statusReason.reason</code>.

A <code class="highlighter-rouge">statusReason</code> <strong>MUST NOT</strong> be generated when an authorisation has simply expired (exceeded review date or number of issues).