# {{page-title}}



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
 

---

### Requirements


---



