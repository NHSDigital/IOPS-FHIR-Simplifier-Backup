## {{page-title}}

```xml
<!-- Dispensed medication #1 -->
<entry>
  <fullUrl value="urn:uuid:0885779a-82e7-11ea-bc55-0242ac130003" />
  <resource>
    <MedicationDispense>
      <id value="0885779a-82e7-11ea-bc55-0242ac130003" />
      <meta>
        <profile
          value="https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-MedicationDispense-1" />
      </meta>
      <status value="completed" />
      <medicationReference>
        <reference value="urn:uuid:f315872e-82e6-11ea-bc55-0242ac130003" />
        <display
          value="Humulin M3 100units/ml suspension for injection 3ml cartridges (CST Pharma Ltd)" />
      </medicationReference>
      <subject>
        <reference value="urn:uuid:1e2b5223-1cd8-43ff-8a67-55dec3edb9b0" />
        <display value="SMITH, William (Mr)" />
      </subject>
      <context>
        <reference value="urn:uuid:adb353f9-0953-4fb4-a4ab-f0ab04a44dbc" />
      </context>
      <performer>
        <actor>
          <reference value="urn:uuid:0e4c13d4-e61f-48f2-89ee-7cf8f5f3dbb3" />
        </actor>
        <onBehalfOf>
          <reference value="urn:uuid:1226082b-315e-40be-83cf-5d21a964219e" />
        </onBehalfOf>
      </performer>
      <type>
        <coding>
          <system value="http://snomed.info/sct" />
          <code value="1218611000000102" />
          <display value="Urgent supply of prescription items by community pharmacy" />
        </coding>
      </type>
      <quantity>
        <extension
          url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-MedicationQuantityText-1">
          <valueString value="2 cartridge" />
        </extension>
        <value value="2" />
        <unit value="cartridge" />
        <system value="http://snomed.info/sct" />
        <code value="732988008" />
      </quantity>
      <daysSupply>
        <value value="14" />
        <unit value="day" />
        <system value="http://unitsofmeasure.org" />
        <code value="d" />
      </daysSupply>
      <whenPrepared value="2018-05-09" />
      <whenHandedOver value="2018-05-09" />
      <dosageInstruction>
        <asNeededBoolean value="true" />
      </dosageInstruction>
    </MedicationDispense>
  </resource>
</entry>

<!-- Dispensed medication #2 -->
<entry>
  <fullUrl value="urn:uuid:42ac049c-87ca-4e33-93ad-987167422b01" />
  <resource>
    <MedicationDispense>
      <id value="42ac049c-87ca-4e33-93ad-987167422b01" />
      <meta>
        <profile
          value="https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-ITK-MedicationDispense-1" />
      </meta>
      <status value="completed" />
      <medicationReference>
        <reference value="urn:uuid:9c7e61c3-5b92-4828-9ebc-21e74bcdbc96" />
        <display
          value="BD Viva hypodermic insulin needles for pre-filled / reusable pen injectors screw on 5mm/31gauge (Becton, Dickinson UK Ltd)" />
      </medicationReference>
      <subject>
        <reference value="urn:uuid:1e2b5223-1cd8-43ff-8a67-55dec3edb9b0" />
        <display value="SMITH, William (Mr)" />
      </subject>
      <context>
        <reference value="urn:uuid:adb353f9-0953-4fb4-a4ab-f0ab04a44dbc" />
      </context>
      <performer>
        <actor>
          <reference value="urn:uuid:0e4c13d4-e61f-48f2-89ee-7cf8f5f3dbb3" />
        </actor>
        <onBehalfOf>
          <reference value="urn:uuid:1226082b-315e-40be-83cf-5d21a964219e" />
        </onBehalfOf>
      </performer>
      <type>
        <coding>
          <system value="http://snomed.info/sct" />
          <code value="1218611000000102" />
          <display value="Urgent supply of prescription items by community pharmacy" />
        </coding>
      </type>
      <quantity>
        <extension
          url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-MedicationQuantityText-1">
          <valueString value="90 needle" />
        </extension>
        <value value="90" />
        <unit value="needle" />
        <system value="http://snomed.info/sct" />
        <code value="3318111000001106" />
      </quantity>
      <daysSupply>
        <value value="14" />
        <unit value="day" />
        <system value="http://unitsofmeasure.org" />
        <code value="d" />
      </daysSupply>
      <whenPrepared value="2018-05-09" />
      <whenHandedOver value="2018-05-09" />
      <dosageInstruction>
        <asNeededBoolean value="true" />
      </dosageInstruction>
    </MedicationDispense>
  </resource>
</entry>
```

---