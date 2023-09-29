## {{page-title}}
The elements available within each FHIR resource are described as follows:

<table data-responsive>
	<thead>
		<tr>
			<th data-no-sort>Icon</th>
			<th>Cardinality</th>
			<th>Labels</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<!-- Mandatory -->
		<tr>
			<td><span class="mro-circle mandatory"></td>
			<td>1....1</td>
			<td>Mandatory</td>
			<td>Must be populated as mandatory in compliance with the FHIR standard</td>
		</tr>
		<!-- Required -->
		<tr>
			<td><span class="mro-circle required"></td>
			<td>0....1</td>
			<td>Required</td>
			<td>Required to be populated if the information is available</td>
		</tr>
		<!-- Optional -->
		<tr>
			<td><span class="mro-circle optional"></td>
			<td>0....*</td>
			<td>Optional</td>
			<td>Information to be provided optionally, often dependent on use case</td>
		</tr>
		<!-- Avoid -->
		<tr>
			<td><span class="mro-circle avoid"></td>
			<td>1....*</td>
			<td>Avoid</td>
			<td>Optional within the FHIR standard and usage <u>should be avoided</u> in this capability</td>
		</tr>
		<!--Unknown -->
		<tr>
			<td><span class="mro-circle unknown"></td>
			<td>N/A</td>
			<td>Unknown</td>
			<td>A decision has not yet been reached regarding the usage for this capability</td>
		</tr>
	</tbody>
</table>

---

## Cardinality

For further cardinality information, please see [Conformance Rules/Cardinality](https://www.england.nhs.uk/primary-care/pharmacy/pharmacy-integration-fund/)