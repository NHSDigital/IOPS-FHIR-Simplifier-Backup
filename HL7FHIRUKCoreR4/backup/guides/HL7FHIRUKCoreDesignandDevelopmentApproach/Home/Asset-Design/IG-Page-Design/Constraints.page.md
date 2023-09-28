## {{page-title}}

Any profile or profile element that has an additional constraint applied SHALL be added to the Constraints (differential) table, via a listing of the key, strength, expression and description of the constraint. 

~~~~html
## Constraints (differential)

More information about the constraints on the <code>UKCore-[profile]</code> profile can be found below.

<table class="assets" title="Constraints list">
<tr>
<th class="width15">Key</th>
<th class="width15">Severity</th>
<th class="width30">Expression</th>
<th class="width40">Human Description</th>
</tr>
<tr>
<td>[constraint key]</td>
<td>[strength]</td>
<td>[fhirpath criteria to be valid]
</td>
<td>[human readable description of valid criteria].</td>
</tr>
</table>

---
~~~~

Elements in the expression SHALL be enclosed in <code>\<code></code> tags, e.g. 
~~~~html
<code>effective</code>.exists() or (<code>effective</code>.empty() and (<code>status</code> in ('partial' | 'preliminary' | 'final' | 'amended' | 'corrected' | 'appended')).not())
~~~~

Where the severity is a <samp>warning</samp>, the Human Description will say SHOULD, where the severity is <samp>error</samp>, it will say SHALL.

---