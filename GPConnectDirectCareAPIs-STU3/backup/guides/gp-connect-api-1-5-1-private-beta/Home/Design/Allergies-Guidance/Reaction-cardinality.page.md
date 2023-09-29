## {{page-title}}

The <code class="highlighter-rouge">AllergyIntolerance.reaction</code> is optional, but where a severity is available in the source system it will be included to convey severity even if no other reaction details are explicitly available. If this is the case the <code class="highlighter-rouge">AllergyIntolerance.reaction.manifestation</code> <strong>MUST</strong> be coded as the <code class="highlighter-rouge">nullFlavor</code> NI.

By convention, only one reaction <strong>MUST</strong> be expressed per allergy with only one manifestation per reaction.
