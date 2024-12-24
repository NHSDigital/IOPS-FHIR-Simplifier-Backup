## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>WARNING</b>: The code 163541000000107 | Dispensed medication is not valid in the "Care Connect List Code" value set and will result in a FHIR validation error.
</div>

```xml
<entry>
    <fullUrl value="urn:uuid:4bc7faea-5974-407a-b658-d6ed1d4c9187"/>
    <resource>
        <List>
            <id value="4bc7faea-5974-407a-b658-d6ed1d4c9187"/>
            <meta>
                <profile value="https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-MedicationDispense-List-1"/>
            </meta>
            <identifier>
                <system value="https://tools.ietf.org/html/rfc4122"/>
                <value value="197987da-97a7-49c2-9657-dac1aea2a461"/>
            </identifier>
            <status value="current"/>
            <mode value="snapshot"/>
            <code>
                <coding>
                    <system value="http://snomed.info/sct"/>
                    <code value="163541000000107"/>
                    <display value="Dispensed Medication"/>
                </coding>
            </code>
            <subject>
                <reference value="urn:uuid:1e2b5223-1cd8-43ff-8a67-55dec3edb9b0"/>
                <display value="SMITH, William (Mr)"/>
            </subject>
            <encounter>
                <reference value="urn:uuid:adb353f9-0953-4fb4-a4ab-f0ab04a44dbc"/>
            </encounter>
            <date value="2018-05-09"/>
            <entry>
                <item>
                    <reference value="urn:uuid:0885779a-82e7-11ea-bc55-0242ac130003"/>
                </item>
            </entry>
            <entry>
                <item>
                    <reference value="urn:uuid:42ac049c-87ca-4e33-93ad-987167422b01"/>
                </item>
            </entry>
        </List>
    </resource>
</entry>
```

---