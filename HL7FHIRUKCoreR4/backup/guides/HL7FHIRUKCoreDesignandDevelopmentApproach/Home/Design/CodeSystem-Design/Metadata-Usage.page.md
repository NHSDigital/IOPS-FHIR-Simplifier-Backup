## {{page-title}}

The list below contains the element differences between the UKCore and HL7. 

{{page:Home/Design/Metadata-Design/Base-Resource-Metadata.page.md}}

### CodeSystem Content

View further information about <a href="https://hl7.org/fhir/R4/codesystem.html#CodeSystem" Target="_blank">FHIR Resource CodeSystem - Content</a>.

{{page:Home/Design/Metadata-Design/Common-Metadata.page.md}}
    <tr>
        <td>caseSensitive</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>boolean</td>
        <td>For all UK Core CodeSystems this SHALL be set to &quot;true&quot; unless a specific use case justifies it being set to &quot;false&quot;. In this case the reasoning for the decision SHALL be added to the description element.</td>
    </tr>
    <tr>
        <td>concept</td>
        <td>0..*</td>
        <td>0..*</td>
        <td>Backbone<br>Element</td>
        <td>Concepts that are in the code system.<br/><br/>Cardinality would normally be 1..* but set to the standard 0..* to allow for a use case where the content element has a value of &quot;not-present&quot;.</td>
    </tr>
    <tr>
        <td>concept<br>.display</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>uri</td>
        <td>This SHALL be included as this presents the concept to a user in a human-readable manner.</td>
    </tr>
  </tbody>
</table>

<br><br>

---

