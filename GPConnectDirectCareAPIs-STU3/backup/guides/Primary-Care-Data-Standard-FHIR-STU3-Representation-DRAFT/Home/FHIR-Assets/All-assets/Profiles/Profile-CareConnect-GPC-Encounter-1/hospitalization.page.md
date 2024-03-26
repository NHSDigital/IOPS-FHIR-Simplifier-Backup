## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

A use-case for population of this element within GP connect has yet to be defined.

<h5><ins>Example</ins></h5>

```xml
<hospitalization>
    <!-- Admission method -->
    <extension>
        <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-AdmissionMethod-1" />
        <valueCodeableConcept>
            <coding>
                <system value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-AdmissionMethod-1" />
                <code value="2A" />
                <display value="Accident and emergency or dental casualty department of the Health Care Provider" />
            </coding>
        </valueCodeableConcept>
    </extension>
    <!-- Discharge method -->
    <extension>
        <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-DischargeMethod-1" />
        <valueCodeableConcept>
            <coding>
                <system value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-DischargeMethod-1" />
                <code value="1" />
                <display value="Patient discharged on clinical advice or with clinical consent" />
            </coding>
        </valueCodeableConcept>
    </extension>

    <preAdmissionIdentifier>
        <use value="official" />
        <type>
            <coding>
                <system value="http://hl7.org/fhir/v2/0203" />
                <code value="MR" />
                <display value="Medical record number" />
            </coding>
        </type>
        <system value="http://www.acme.com/identifiers/patient" />
        <value value="60ebba04-f4b9-40d3-b3d3-ee26fad7cfe6" />
        <period>
            <start value="2022-10-28T23:06:00+00:00" />
            <end value="2022-10-28T23:10:00+00:00" />
        </period>
        <assigner>
            <reference value="organisation-12320fsdp" />
        </assigner>
    </preAdmissionIdentifier>
    <origin>
        <reference value="location-ward-23" />
    </origin>
    <admitSource>
        <coding>
            <system value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-SourceOfAdmission-1" />
            <code value="49" />
            <display value="NHS other Hospital Provider - high security psychiatric accommodation in an NHS Hospital Provider (NHS Trust or NHS Foundation Trust)" />
        </coding>
    </admitSource>
    <reAdmission>
        <coding>
            <system value="http://hl7.org/fhir/v2/0092" />
            <code value="R" />
            <display value="Re-admission" />
        </coding>
    </reAdmission>
    <dietPreference>
        <coding>
            <system value="http://hl7.org/fhir/diet" />
            <code value="vegan" />
            <display value="Vegan" />
        </coding>
    </dietPreference>
    <specialCourtesy>
        <coding>
            <system value="http://hl7.org/fhir/v3/EncounterSpecialCourtesy" />
            <code value="NRM" />
            <display value="normal courtesy" />
        </coding>
    </specialCourtesy>
    <specialArrangement>
        <coding>
            <system value="http://hl7.org/fhir/encounter-special-arrangements" />
            <code value="wheel" />
            <display value="Wheelchair" />
        </coding>
    </specialArrangement>
    <destination>
        <reference value="location-93tryu1" />
    </destination>
    <dischargeDisposition>
        <system value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-DischargeDestination-1" />
        <code value="66" />
        <display value="Local Authority foster care" />
    </dischargeDisposition>
</hospitalization>
```

---