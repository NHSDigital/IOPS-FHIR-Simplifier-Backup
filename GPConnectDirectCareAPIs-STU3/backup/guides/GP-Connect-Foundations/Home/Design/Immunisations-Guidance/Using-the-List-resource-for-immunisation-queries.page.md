## {{page-title}}

The results of a query for immunisation details <strong>MUST</strong> return a <code class="highlighter-rouge">List</code> containing references to all <code class="highlighter-rouge">Immunization</code> and <code class="highlighter-rouge">Observation</code> resources that are returned.</p>

The <code class="highlighter-rouge">List</code> <strong>MUST</strong> be populated in line with the guidance on <code class="highlighter-rouge">List</code> resources.

If the <code class="highlighter-rouge">List</code> is empty, then an empty <code class="highlighter-rouge">List</code> <strong>MUST</strong> be returned with an <code class="highlighter-rouge">emptyReason.code</code> with the value <code class="highlighter-rouge">no-content-recorded</code>. In this case, <code class="highlighter-rouge">List.note</code> <strong>MUST</strong> be populated with the text ‘Information not available’.

