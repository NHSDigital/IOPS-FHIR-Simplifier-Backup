# {{page-title}}

This example, taken from Sprint 6 was used to illustrate the use case requirements.

## Welsh Results Reporting Service (WRRS)

### Business use case

This project will replace legacy SOAP interfaces provided by the WRRS that support diagnostic test requesting and results reporting functionality.
The development of a FHIR API for WRRS is line with the NHS Wales strategy to implement an open and standards based health and care architecture.
The Project requires derived profiles to facilitate viewing laboratory reports in a structured way. The expectation is that each derived profile will have the suffix ‘Lab’ to differentiate them from other profiles. 
It will require UK Core IG guidance and profiles for the following FHIR resource types:
- DiagnosticReport
- Observation
- ImagingStudy
- ServiceRequest
- Specimen

#### View list of a patient’s test reports

**As a clinician, I want**
- To view a list of test results and reports for a patient<br>

**So that**
- I can select a test result or report from the list to view further information.

<br><br>
**Actors**
1. Clinician (e.g. hospital Doctor, GP)
2. Software system(s) containing diagnostic test results and reports (e.g. NHS Wales Results Reporting System)

**Triggers**

The clinician has opened the patient record within a clinical portal or similar application, and elects to view the patient’s test results

**Pre Conditions**
1. Patient has been searched and found.
2. An identifier (e.g. NHS number, CRN) for the patient is determined.
3. Clinician opens patient record.
4. Clinician elects to view patient test results

**Post Conditions**
1. Clinical user is presented with a list of test results and reports, including:
    a. Lab results,
    b. Radiology/imaging,
    c. Other result reports e.g. ECG, Cardiology
2. User can select and view a test result from the list

**Main Course**
1. In order to provide care, a clinician uses a clinical portal or similar application to view the patient record.
2. Using the portal, the clinician elects to view test results for the patient.
3. Clinician is presented with a list of test results and reports, including: Lab and other pathology results, Radiology/imaging, Other results e.g. ECG, Cardiology
4. Clinician can select and view a test result from the list

**Alternate Course**

1. The clinician elects to view a filtered set of test reports (e.g. wishes to view radiology reports only)
2. Clinician uses demographic details to search for and view test results and reports.

**Exception**

1. Patient record is unavailable.
2. Test results are unavailable.
3. Clinician cannot access online systems

--- 

### Workflow

#### *Overview*
 
{{render:Lab-Overview}}




#### *Imaging Investigation Result Structure*
{{render:Lab-Imaging-Result}}
 

#### *Cardiology Result (as embedded PDF)*
 {{render:Lab-Cardiology-Result}}



#### *Laboratory Test Result Structure*
 {{render:Derived-Profiles-Lab-Example}}


---

### Requirements
- A fixed code of ‘LAB’ should be included as a category code.
- Because lab reports can be modelled in several different ways, the DiagnosticReport profile and IG guidance should specify a structure – i.e.
- Test results are carried in Observation Groups e.g. U&R, eGFR, Full Blood count etc. 
- Observation groups contain nested result item Observations (and not components).
- Result item Observations can be used to graph a series of test result items.
- Observations should contain a code (preferably a SNOMED code from the Unified Test List) to tell you what is being measured.

---

### Example
See *Laboratory Test Result Structure* for preliminary example

Examples created in FHIR

#### **DiagnosticReport-Lab**

``` xml
<DiagnosticReport xmlns="http://hl7.org/fhir">
    <id value="UKCore-DiagnosticReport-Lab-DiagnosticStudiesReport-Example" />
    <identifier>
        <system value="https://tools.ietf.org/html/rfc4122" />
        <value value="727071dc-eb01-4224-8ee8-cc0a029787ac" />
    </identifier>
    <status value="final" />
    <category>
        <coding>
            <system value="http://terminology.hl7.org/CodeSystem/v2-0074" />
            <code value="LAB" />
            <display value="Laboratory" />
        </coding>
    </category>
    <code>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="721981007" />
            <display value="Diagnostic studies report" />
        </coding>
    </code>
    <subject>
        <reference value="Patient/UKCore-Patient-RichardSmith-Example" />
    </subject>
    <effectiveDateTime value="2023-01-13T14:53:23+00:00" />
    <performer>
        <reference value="Organization/UKCore-Organization-LeedsTeachingHospital-Example" />
        <display value="LEEDS TEACHING HOSPITALS NHS TRUST" />
    </performer>
    <specimen>
        <reference value="Specimen/UKCore-Specimen-BloodSpecimen-Example" />
    </specimen>
    <result>
        <reference value="UKCore-Observation-Group-FullBloodCount-Example" />
    </result>
</DiagnosticReport>
```

#### **Observation-LabGroup**
``` xml
<Observation xmlns="http://hl7.org/fhir">
    <id value="UKCore-Observation-Group-FullBloodCount-Example" />
    <identifier>
        <system value="https://tools.ietf.org/html/rfc4122" />
        <value value="53dd97da-082c-450d-a47d-3ffa44941a68" />
    </identifier>
    <status value="final" />
    <category>
        <coding>
            <system value="http://terminology.hl7.org/CodeSystem/observation-category" />
            <code value="laboratory" />
            <display value="Laboratory" />
        </coding>
    </category>
    <code>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="26604007" />
            <display value="Full blood count" />
        </coding>
    </code>
    <subject>
        <reference value="Patient/UKCore-Patient-RichardSmith-Example" />
    </subject>
    <hasMember>
        <reference value="Observation/UKCore-Observation-Lab-WhiteCellCount-Example" />
    </hasMember>
    <hasMember>
        <reference value="Observation/UKCore-Observation-Lab-RedCellCount-Example" />
    </hasMember>
</Observation>
```

#### **Observation-Lab**

```xml
<Observation xmlns="http://hl7.org/fhir">
    <id value="UKCore-Observation-Lab-RedCellCount-Example" />
    <identifier>
        <system value="https://tools.ietf.org/html/rfc4122" />
        <value value="fcd8af5a-18a0-4d0b-8c79-5b6bdf55fb32" />
    </identifier>
    <status value="final" />
    <category>
        <coding>
            <system value="http://terminology.hl7.org/CodeSystem/observation-category" />
            <code value="laboratory" />
            <display value="Laboratory" />
        </coding>
    </category>
    <code>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="58571000237106" />
            <display value="Nucleated red blood cell count in blood" />
        </coding>
    </code>
    <subject>
        <reference value="Patient/UKCore-Patient-RichardSmith-Example" />
    </subject>
    <performer>
        <reference value="Organization/UKCore-Organization-LeedsTeachingHospital-Example" />
    </performer>
    <valueQuantity>
        <value value="3.9" />
        <unit value="10*12/L" />
        <system value="http://unitsofmeasure.org" />
    </valueQuantity>
    <specimen>
        <reference value="Specimen/UKCore-Specimen-BloodSpecimen-Example" />
    </specimen>
    <referenceRange>
        <low>
            <value value="4.0" />
        </low>
        <high>
            <value value="5.9" />
        </high>
    </referenceRange>
</Observation>
```

#### **Observation-Lab**

```xml
<Observation xmlns="http://hl7.org/fhir">
    <id value="UKCore-Observation-Lab-WhiteCellCount-Example" />
    <identifier>
        <system value="https://tools.ietf.org/html/rfc4122" />
        <value value="3b809516-a294-4de9-a4ce-0c24c7b5f796" />
    </identifier>
    <status value="final" />
    <category>
        <coding>
            <system value="http://terminology.hl7.org/CodeSystem/observation-category" />
            <code value="laboratory" />
            <display value="Laboratory" />
        </coding>
    </category>
    <code>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="16181000237107" />
            <display value="White blood cell count in fluid" />
        </coding>
    </code>
    <subject>
        <reference value="Patient/UKCore-Patient-RichardSmith-Example" />
    </subject>
    <performer>
        <reference value="Organization/UKCore-Organization-LeedsTeachingHospital-Example" />
    </performer>
    <valueQuantity>
        <value value="11.2" />
        <unit value="10*9/L" />
        <system value="http://unitsofmeasure.org" />
    </valueQuantity>
    <specimen>
        <reference value="Specimen/UKCore-Specimen-BloodSpecimen-Example" />
    </specimen>
    <referenceRange>
        <low>
            <value value="4.0" />
        </low>
        <high>
            <value value="17.0" />
        </high>
    </referenceRange>
</Observation>
```

---

