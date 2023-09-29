## How to construct bundle

The Bundle resource is used to structure the data.

## Mapping Table

### Bundle
|V3|FHIR | |
|--
|`<code codeSystem="2.16.840.1.113883.2.1.3.2.4.15" code="196981000000101" displayName="General Practice Summary"/>`|`<type><coding><system value="http://snomed.info/sct"/><code value="196981000000101"/><display value="General Practice Summary"/></coding></type>`|M|
|`<effectiveTime value="200703150100"/>`|`<date value="2007-03-15T01:00:00Z"/>`|M|
|`<agentPersonSDS determinerCode="INSTANCE" classCode="PSN"><id root="1.2.826.0.1285.0.2.0.65" extension="984181387037"/><name>Dr Steve Jones</name></agentPersonSDS>`|`<author><reference value="urn:uuid:83c26c8f-ee72-4534-8891-0136972b2106"/><display value="Dr Steve Jones"/></author>`|M|
|`<presentationText classCode="OBS" moodCode="EVN"><value mediaType="text/plain" xsi:type="ED.NPfIT.Text.XHTML"><html xmlns="xhtml:NPfIT:PresentationText"><head/><body><h2>General Practice  Summary</h2>`|`<section><title value="General Practice Summary"/><text><status value="generated"/>`|M|

### Composition
|v3|FHIR | |
|--
|`<h2>Allergies and Adverse Reactions</h2><table><thead><tr><th>Date</th><th>Description</th><th>Supporting information</th></tr></thead><tbody><tr><td>13-Jan-07</td><td>Refused consent for upload to national shared electronic record</td></tr><tr><td>14-Nov-06</td><td>Allergy to Drug - Penicillin, (probably present) . </td><td>Patient stated that they told that they were were allergic to penicillin by their parents </td></tr></tbody></table>`|`<section><title value="Allergies and Adverse Reactions"/><text><status value="generated"/><div xmlns="http://www.w3.org/1999/xhtml"><table><thead><tr><th>Date</th><th>Description</th><th>Supporting information</th></tr></thead><tbody><tr><td>13-Jan-07</td><td>Refused consent for upload to national shared electronic record</td></tr><tr><td>14-Nov-06</td><td>Allergy to Drug - Penicillin, (probably present) . </td><td>Patient stated that they told that they were were allergic to penicillin by their parents </td></tr></tbody></table></div></text></section>`|M|
