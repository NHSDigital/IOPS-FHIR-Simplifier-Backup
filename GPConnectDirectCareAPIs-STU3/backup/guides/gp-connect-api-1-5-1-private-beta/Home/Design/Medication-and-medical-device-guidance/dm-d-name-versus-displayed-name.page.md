## {{page-title}}

It is possible for historic/legacy medications/medical devices to be displayed with a name corresponding to the name in the original system’s drug dictionary rather than the dm+d name. This name <strong>MUST</strong> be preserved via <code class="highlighter-rouge">CodeableConcept.text</code> when representing the medication via resources. <code class="highlighter-rouge">CodeableConcept.text</code> is redundant when the displayed medication/medical device name on the original system and the dm+d name is identical, and, in these cases, <code class="highlighter-rouge">CodeableConcept.text</code> <strong>MUST</strong> be omitted.

