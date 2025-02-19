## {{page-title}}

The following scenarios have been captured to indicate various specialist testing scenarios associated with testing for either the woman or the fetus:

<table class="assets">
  <th style="width:70%">Scenario</th><th>Modelling Considerations</th>
  <tr>
    <td>
<ul><li><b>Woman is pregnant and testing is on woman (e.g., prenatal testing):</b> The test request is created on the fetal record and the sample taken is from the woman</li>
<li>Confirmation of if the woman has been diagnosed with cancer or is undergoing treatment becomes mandatory</li></ul>
    </td>
    <td>
In this case, the data model SHOULD match the singleton scenario (Fetus is the Proband, however testing is on the woman's sample only)
    </td>
  </tr>
  <tr>
    <td>
<ul><li><b>Woman is pregnant and the specialist testing is on the woman (e.g., NIPD):</b> The test request is created on the fetal record and the sample taken is from the woman</li>
<li>NIPD would also require a paternal sample and cord blood or fetal tissue post delivery</li>
<li>Confirmation of if the woman has been diagnosed with cancer or is undergoing treatment becomes mandatory</li></ul>
    </td>
    <td>
In this case, the data model SHOULD match the singleton/duo/trio scenario (Fetus is the Proband and testing is on the woman's, man's or fetal sample as appropriate)
    </td>
  </tr>
  <tr>
    <td>
<ul><li><b>Woman is pregnant and testing is on the fetus (e.g., CVS or amnio):</b> The test requested is created on the fetal record. As part of fetus testing, the following information becomes mandatory:</li>
<li>Woman's sample may be required for MCC (regardless of whether the condition is paternal), see R321.1</li>
<li>the ability  to register a test against the fetus (this may differ from local organisation to another and is typically the woman’s Hospital ID plus indication of fetus ( Ex. WG1342Fetus A) - <b>Used as the unique fetal identifier prior to NHS Number allocation</b></li>
<li>The capture of additional information such as fetal phenotypic sex (M/F/U or Unknown) and number of fetuses also becomes mandatory. - <b>Captured on the Patient resource for the foetus</b></li>
<li>Pregnancy details: capture of Pregnancy type (Spontaneous conception, Surrogacy, or IVF Pregnancy). If IVF, the capture of own/donor egg/sperm and the age of the egg donor becomes mandatory - <b>Observation resources linked to the woman's patient record, as they relate to the pregnancy</b></li>
<li><b>Note:</b> If fetus is under 24 weeks, the sample is from the woman (as fetal viability is from 24 weeks as per UK law) - <b>in this case the Proband (fetus) does not have any samples associated with their record.</b></li></ul>
    </td>
    <td>
In this case, the data model SHOULD match the singleton/duo scenario (Fetus is the Proband, woman's record is captured through additional RelatedPerson and Patient records attached to ServiceRequest.supportingInfo, testing may be on both fetal and maternal samples but may be on maternal samples only).
    </td>
  </tr>
  <tr>
    <td>
<ul><li><b>Woman is pregnant with multiple fetuses and test is completed on each fetus with a result per fetus:</b> An electronic test request <b>per fetus</b> is created on the fetal record.  A test request/sample collection is required for each fetus. Additional mandatory information required includes:</li>
<li>the ability  to register a test against the fetus (this may differ from local organisation to another and is typically the woman’s Hospital ID plus indication of fetus (Ex. WG1342Fetus A) - <b>Used as the unique fetal identifier prior to NHS Number allocation</b></li>
<li>The capture of additional information such as fetal phenotypic sex (M/F/Unclear or Unknown) and number of fetuses also becomes mandatory. - <b>Captured on the Patient resource for the fetus</b></li>
<li>Pregnancy details: capture of Pregnancy type (Spontaneous conception, Surrogacy, or IVF Pregnancy). If IVF, the capture of own/donor egg/sperm and the age of the egg donor becomes mandatory - <b>Observation resources linked to the woman's patient record, as they relate to the pregnancy</b></li></ul>
    </td>
    <td>
In this case, the data model SHOULD be equivalent to multiple singleton/duo tests (Fetus is the Proband for each test, woman's record is captured through additional RelatedPerson and Patient records attached to ServiceRequest.supportingInfo, testing may be on both fetal and maternal samples but may be on maternal samples only). Tests can possibly be linked via a shared requisition identifier on each ServiceRequest (pending further testing)
    </td>
  </tr>
  <tr>
    <td>
<ul><li><b>Woman is pregnant and has had a miscarriage:</b> In these scenarios, further testing may be required to inform the management of future pregnancies. Testing may occur on the woman, fetus or sample from the previous pregnancy (if available).  A test request is created on the <b>woman’s</b> record with the confirmation of sample collected (if after 24 weeks as fetal tissue or cord blood)</li></ul>
    </td>
    <td>
In this case, the data model SHOULD match the singleton/duo scenario (Woman is the Proband, as testing is for the benefit of the woman, with foetal information captured through additional RelatedPerson and Patient records attached to the ServiceRequest). If samples from the previous miscarriage are tested, these should be added as pre-existing Specimens to the ServiceRequest (as per the DNA Storage, using stored sample example)
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

### 2. Requester (e.g. Midwife) to search for appropriate specialist testing description or code

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

### The lab receives the test request and:

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