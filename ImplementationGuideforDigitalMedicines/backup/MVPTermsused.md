## {{page-title}}

The elements available within each FHIR resource are described as follows;

<table data-responsive>
	<thead>
		<tr>
			<th data-no-sort>Icon</th>
			<th>MVP</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<!-- Mandatory -->
		<tr>
			<td><span class="mro-circle mandatory"></td>
			<td>Mandatory</td>
			<td>Must be populated as mandatory as per the FHIR standard.</td>
		</tr>
		<!-- Must-support -->
		<tr>
			<td><span class="mro-circle required"></td>
			<td>Must support</td>
			<td>Where a Must support flag is present on a resource element, a consumer system <strong>shall</strong> populate the field in the request body if data is available to do so, irrespective of the fact that field cardinality may be <code>0..1</code> or <code>0..*</code>.</td>
		</tr>
		<!-- Optional -->
		<tr>
			<td><span class="mro-circle optional"></td>
			<td>Optional</td>
			<td>Optional within the FHIR standard which do not form part of the recommended MVP.</td>
		</tr>
		<!-- Avoid -->
		<tr>
			<td><span class="mro-circle avoid"></td>
			<td>Avoid</td>
			<td>Optional within the FHIR standard and usage <u>should be avoided</u> in an MVP.</td>
		</tr>
		<!--Unknown -->
		<tr>
			<td><span class="mro-circle unknown"></td>
			<td>Unknown</td>
			<td>A decision has not yet been reached regarding the usage for an MVP.</td>
		</tr>
	</tbody>
</table>

---
