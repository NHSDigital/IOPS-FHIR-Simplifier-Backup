## {{page-title}}

The logical structure of a Consultation is reflected in FHIR using the `Encounter` and `List` profiles.

<table data-responsive class="nhsd-!t-margin-bottom-6">
    <thead>
        <th data-no-sort>Logical structure</th>
        <th data-no-sort>FHIR profile</th>
        <th data-no-sort>Description</th>
    </thead>
    <tbody>
        <tr>
            <td>Context</td>
            <td>Encounter</td>
            <td>The context information is held in the Encounter profile</td>
        </tr>
        <tr>
            <td></td>
            <td>List</td>
            <td>The clinical information is grouped and organised within multiple List profiles. The top level list contains references to each of the Topics within the Consultation.</td>
        </tr>
        <tr>
            <td>Topic</td>
            <td>List</td>
            <td>Each Topic is held as a List containing references to each of the Headings under the Topic.<br />Where a Topic does not contain Headings the List directly references Clinical Items.</td>
        </tr>
        <tr>
            <td>Heading</td>
            <td>List</td>
            <td>Each Heading is held as a List containing references to each of the CLinical items under the Heading</td>
        </tr>
        <tr>
            <td>Clinical Items</td>
            <td>Appropriate FHIR profile</td>
            <td>Each Clinical Item will be held in the appropriate FHIR profile as defined eslewhere in this data model</td>
        </tr>
    </tbody>
</table>

---