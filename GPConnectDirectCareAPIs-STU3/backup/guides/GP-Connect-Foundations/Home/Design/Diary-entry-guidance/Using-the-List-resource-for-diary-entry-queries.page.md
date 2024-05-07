## {{page-title}}

<p>The results of a query for diary entry details <strong>MUST</strong> return a <code class="highlighter-rouge">List</code> containing references to all <code class="highlighter-rouge">ProcedureRequest</code> resources that are returned.</p>

<p>The <code class="highlighter-rouge">List</code> <strong>MUST</strong> be populated in line with the guidance on <code class="highlighter-rouge">List</code> resources.</p>

<p>If the <code class="highlighter-rouge">List</code> is empty, then an empty <code class="highlighter-rouge">List</code> <strong>MUST</strong> be returned with an <code class="highlighter-rouge">emptyReason</code> with the value <code class="highlighter-rouge">no-content-recorded</code>.</p>

