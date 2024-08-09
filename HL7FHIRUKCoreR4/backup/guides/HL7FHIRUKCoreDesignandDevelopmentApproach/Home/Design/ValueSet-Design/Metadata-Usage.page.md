## {{page-title}}

The list below contains the element differences between the UKCore and HL7. 

{{page:Home/Design/Metadata-Design/Base-Resource-Metadata.page.md}}

### Resource ValueSet - Content

View further information about <a href="https://hl7.org/fhir/R4/valueset.html" Target="_blank">Resource ValueSet - Content</a>.

{{page:Home/Design/Metadata-Design/Common-Metadata.page.md}}
    <tr>
        <td>compose</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>BackboneElement</td>
        <td>See the {{pagelink:Content-Logical-Definition}} for details on how to populate this.</td>
    </tr>
    <tr>
        <td>compose<br>.include<br>.concept<br>.display</td>
        <td>0..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>This element SHALL be used in the UKCore</td>
    </tr>
    <tr>
        <td>compose<br>.include<br>.filter<br>.property</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>code</td>
        <td>For UK Core ValueSets containing SNOMED CT concepts encapsulated within an ECL expression, the <code>constraint</code> value SHALL used.</td>
    </tr>
    <tr>
        <td>compose<br>.include<br>.filter<br>.value</td>
        <td>1..1</td>
        <td>1..1</td>
        <td>string</td>
        <td>Due to some systems having difficulties processing symbols, for UK Core ValueSets containing SNOMED CT concepts encapsulated within an ECL expression, the long syntax SHALL be used. The SNOMED CT term SHALL NOT be suffixed to the SCTID.</td>
        </tr> 
  </tbody>
</table>

---

