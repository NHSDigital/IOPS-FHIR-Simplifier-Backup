## {{page-title}}

<table class="assets">
<tr>
<th class="width20">Date</th>
<th class="width20">IG Version</th>
<th class="width20">NHSE Package Version</th>
<th class="width20">UK Core Version</th>
<th class="width20">FHIR Version</th>
</tr>
<tr>
<td>28th November 2023</td>
<td>1.0.1</td>
<td>STU1 1.0.0</td>
<td>STU3 0.0.6</td>
<td>4.0.1</td>
</tr>
<tr>
<td colspan="5">Initial release of the Multi-cancer Early Detection Implementation guide.</td>
</tr>
<tr>
<td colspan="5"><b>Changes for this version (1.0.0)</b>
<br />

<b>Validated Examples</b>

<ul>
<li>Anonymised examples</li>
<li>Practitioner.name.suffix moved to text</li>
<li>Lab notes all now in DiagnosticReport extension</li>
<li>All performer references point to Lag Organization</li>
<li>All specimen references have specimen identifier in display</li>
<li>Detected site SNOMED display changed to "Multi-cancer early detection predicted first cancer signal origin by machine learning-based classifier"<br/>"Multi-cancer early detection predicted second cancer signal origin by machine learning-based classifier"</li>
<li>Data mapping table updated to reference generic screening organisation identifiers</li>
</ul>
</td>
</tr>
<tr>
<td colspan="5"><b>Changes for this version (1.0.1)</b>
<br />
<b>Removed specific body sites examples from mapping page</b>
<ul>
<li>Mapping table now states that any body site from the SNOMED hierachy < 123037004 | Body structure (body structure) can be used to represent body sites where cancer signals are detected. Also includes guidance on how to represent multiple body sites for primary and secondary locations.</li>
<li>Examples further anonymised</li>
<li>Mapping table & examples updated with missing SNOMED CT codes added for<br>1854971000000106	| Qualitative result of cancer methylation profile in cell free deoxyribonucleic acid by next generation sequencing<br/>1854981000000108 | Multi-cancer early detection signal detected<br/>1854991000000105 | Multi-cancer early detection signal not detected<br/>1873921000000106 | Multi-cancer early detection highest probability cancer signal origin by machine learning-based classifier<br/>1873931000000108 | Multi-cancer early detection second highest probability cancer signal origin by machine learning-based classifier</li>
</ul>
</td>
</tr>
</table>