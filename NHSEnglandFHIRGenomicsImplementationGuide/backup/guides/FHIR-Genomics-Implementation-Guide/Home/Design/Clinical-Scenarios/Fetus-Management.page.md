## {{page-title}}

The following scenarios have been captured to indicate various specialist testing scenarios associated with testing for either the mother or the fetus:

<table class="assets">
  <th style="width:70%">Scenario</th><th>Modelling Considerations</th>
  <tr>
    <td>
<ul><li><b>Mother is pregnant and testing is on mother (e.g., prenatal testing):</b> The test request is created on the mother’s record and the sample taken is from the mother.</li>
<li>Confirmation of if the patient has been diagnosed with cancer or is undergoing treatment becomes mandatory </li></ul>
    </td>
    <td>
In this case, the data model SHOULD match the singleton scenario (Mother is the Proband and testing is on the mother only).
    </td>
  </tr>
  <tr>
    <td>
<ul><li><b>Mother is pregnant and the specialist testing is on the mother (e.g., NIPD):</b> The test request is created on the mother’s record and the sample taken is from the mother.</li>
<li>Confirmation of if the patient has been diagnosed with cancer or is undergoing treatment becomes mandatory </li></ul>
    </td>
    <td>
In this case, the data model SHOULD match the singleton scenario (Mother is the Proband and testing is on the mother only).
    </td>
  </tr>
  <tr>
    <td>
<ul><li><b>Mother is pregnant and testing is on the Fetus (e.g., CVS or amnio):</b> The test requested is created on the <b>foetal</b> record. As part of fetus testing, the following information becomes mandatory:</li>
<li>the ability  to capture test on the fetus (this may differ from local organisation to another and is typically the Mother’s Hospital ID plus indication of fetus ( Ex. WG1342Fetus A) - <b>Used as the unique foetal identifier prior to NHS Number allocation</b></li>
<li>The capture of additional information such as foetal phenotypic sex (M/F/U or Unknown) and number of fetuses also becomes mandatory. - <b>Captured on the Patient resource for the foetus</b></li>
<li>Pregnancy details: capture of Pregnancy type ( Spontaneous conception, Surrogacy, or IVF Pregnancy). If IVF, the capture of own egg/sperm and the age of the egg donor becomes mandatory - <b>Observation resources linked to the Mother's patient record, as they relate to the pregnancy</b></li>
<li><b>Note:</b> If fetus is under 24 weeks, the sample is from the mother - <b>in this case the Proband (foetus) does not have any samples associated with their record.</b></li></ul>
    </td>
    <td>
In this case, the data model SHOULD match the singleton/duo scenario (Foetus is the Proband, Mother's record is captured through additional RelatedPerson and Patient records attached to ServiceRequest.supportingInfo, testing may be on both foetal and maternal samples but may be on maternal samples only).
    </td>
  </tr>
  <tr>
    <td>
<ul><li><b>Mother is pregnant, multiple fetuses and test is completed on each fetus with a result per fetus:</b> An electronic test request <b>per foetus</b> is created on the <b>foetal</b> record.  A test request/ sample collection  is required for each fetus. Additional mandatory information required includes:</li>
<li>the ability  to capture test on the fetus (this may differ from local organisation to another and is typically the Mother’s Hospital ID plus indication of fetus ( Ex. WG1342Fetus A) - <b>Used as the unique foetal identifier prior to NHS Number allocation</b></li>
<li>The capture of additional information such as foetal phenotypic sex (M/F/U or Unknown) and number of fetuses also becomes mandatory. - <b>Captured on the Patient resource for the foetus</b></li>
<li>Pregnancy details: capture of Pregnancy type (Spontaneous conception, Surrogacy, or IVF Pregnancy). If IVF, the capture of own egg/sperm and the age of the egg donor becomes mandatory - <b>Observation resources linked to the Mother's patient record, as they relate to the pregnancy</b></li></ul>
    </td>
    <td>
In this case, the data model SHOULD be equivalent to multiple singleton/duo tests (Foetus is the Proband for each test, Mother's record is captured through additional RelatedPerson and Patient records attached to ServiceRequest.supportingInfo, testing may be on both foetal and maternal samples but may be on maternal samples only). Tests can possibly be linked via a shared requisition identifier on each ServiceRequest (pending further testing)
    </td>
  </tr>
  <tr>
    <td>
<ul><li><b>Mother is pregnant and has had a miscarriage:</b> In certain scenarios, where further testing may be required on the fetus to inform the management on future pregnancies, testing may occur on the fetus.  A test request is created on the mother’s record with the confirmation of sample collected (if after 24 weeks as skin on cord).  </li></ul>
    </td>
    <td>
In this case, the data model SHOULD match the singleton/duo scenario (Mother is the Proband, as testing is for the benefit of the mother, with foetal information captured through additional RelatedPerson and Patient records attached to the ServiceRequest). If samples from the previous miscarriage are tested, these should be added as pre-existing Specimens to the ServiceRequest (as per the DNA Storage, using stored sample example)
    </td>
  </tr>
</table>
The requirement for electronic test order forms is to allow for configuration of specialist testing requirements and enable the management of samples associated with the fetus. Further input is required from the GMS to confirm the scenario as part of the testing phase within the Alpha.

### [Link to the High Fidelity Wireframe for the Fetal Scenario](https://mfy3qt.axshare.com/)

The following steps is a walk through of:

### 1. Requester (e.g Midwife) searches for woman (a dummy patient has been pre-populated as an example)

**Parameters:**
```
given=Ryanne
family=Boulder
birthdate=eq1980-09-02
```

**Response:**

{{pagelink:Patient-RyanneBoulder-Example}}

### 2. Requester (e.g. Midwife) to search for approrpiate specialist testing description or code

ServiceRequest.code = R21

### 3. Requester (e.g.Midwife) completes the Non WGS Rare Disease Test Order Form (with specialist requirement) and submit the request

**POST transaction Bundle to GMS baseURL:**

{{pagelink:Bundle-NonWGSTestOrderForm-FetalScenario-Example}}

and subsequent POST with updated reference for Paternal Sample:

{{pagelink:Bundle-NonWGSTestOrderFormUpdated-FetalScenario-Example}}

**Note: The Test Order is related to {{pagelink:Patient-FoetusOfRyanneBoulder-Example}} with Ryanne Boulder linked to the resource through a RelatedPerson**

**Response:**

OperationOutcome with appropriate success/failure codes: {{pagelink:OperationOutcome-SuccessfulValidation-Example}}

### 4. Requester indicates that sample is going to be collected at a later date

Indicated through absence of Specimen resource in message or absence of ```Specimen.collectedDateTime```/```Specimen.status=unavailable```

Specific Observation, Specimen and Procedure resources related to the above request can be found on the relevant Example pages.

### The lab recieves the test request and:

### 1. Views the completed test order form

Obtained through GET /ServiceRequest or /GET Task requests (using parameters on {{pagelink:Home/FHIRAssets/CapabilityStatements}} to filter results) for non-routed requests. (Dashboard of available requests)

OR

Obtained through GET /Task request (filtered by GLH owner) for routed requests.

Then

GET /Task by Id and referenced ServiceRequest for view of individual.

### 2. Accepts the test request

PUT of {{pagelink:Task-NonWGSRareDiseaseTestOrderAccepted-FetalScenario-Example}}

OR

### 3. Rejects the test request 

PUT of {{pagelink:Task-NonWGSRareDiseaseTestOrderRejected-FetalScenario-Example}}

OR

### 4. Modifies the test request

POST of {{pagelink:ServiceRequest-NonWGSTestOrderFormUpdated-FetalScenario-Example}}

and {{pagelink:Provenance-NonWGSTestOrderForm-FetalScenario-Example}}

in a Transaction Bundle