---
topic: DataMapping
---
## Data Mapping

### FHIR to PMIP EDIFACT (NHS003) Mappings
The following tables define a set of mappings between the FHIR profiles that are described by this implementation guide and the [PMIP EDIFACT (NHS003)](https://webarchive.nationalarchives.gov.uk/20150107145848/http://www.isb.nhs.uk/documents/isb-1557/amd-39-2003) messaging specification.  Whilst every effort has been made to ensure that the mappings are correct, they are not a normative part of the implementation guidance. They are intended to provide additional guidance to suppliers who are familiar with the existing PMIP EDIFACT (NHS003) specification.

The constraints that need to be applied to each FHIR resource using the relevant UK Core profiles are described in the individual profile pages (refer to the {{pagelink:FHIRAssetsR4Profiles}} section of this implementation guide). Only those FHIR data elements that are currently in scope (as defined in the Additional Guidance section of each profile page) are listed in the tables below. 

### UKCore-DiagnosticReport-Lab

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4DiagnosticReport}}</th>   
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td>E184</td>
            <td>identification of laboratory service report by laboratory service provider</td>
            <td>SG2.RFF.C506.1154</td>
            <td></td>
        </tr>
        <tr>
            <td>basedOn</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>status</td>
            <td>E186</td>
            <td>status of laboratory service</td>
            <td>SG2.STS.C555.9011</td>
            <td>'STATUS EVENT' (status of laboratory service report) is always set to 'UN' (Unspecified). Refer to the description of 'STATUS EVENT' (tag id C555) in LSR_04_A_001.doc.</td>
        </tr>
        <tr>
            <td>category</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>code</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>subject</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>issued</td>
            <td>E185</td>
            <td>issue date and time of laboratory service report</td>
            <td>SG2.DTM.C507.2380</td>
            <td></td>
        </tr>
        <tr>
            <td>performer</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>specimen</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>result</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>conclusion</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>conclusionCode</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
   </tbody>
</table>

<br>

### UKCore-Observation-Group-Lab (Test Group)

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4ObservationTestGroup}}</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>status</td>
            <td>E139</td>
            <td>status of laboratory investigation (result item)</td>
            <td>SG18.STS.C555.9011</td>
            <td></td>
        </tr>
        <tr>
            <td>category</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>code.coding.code</td>
            <td>E108</td>
            <td>measurable quantity attribute</td>
            <td>SG18.INV.C847.9931</td>
            <td></td>
        </tr>
        <tr>
            <td>code.coding.system</td>
            <td>E108</td>
            <td>code list specifying the measurable quantity attribute</td>
            <td>SG18.INV.C847.1131</td>
            <td></td>
        </tr>
        <tr>
            <td>code.coding.display</td>
            <td>E108</td>
            <td>textual representation of the code for measurable quantity attribute</td>
            <td>SG18.INV.C847.9930</td>
            <td></td>
        </tr>
        <tr>
            <td>subject</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>effective[x]</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>issued</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>performer</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>note</td>
            <td>E141</td>
            <td>comment to laboratory investigation result item</td>
            <td>SG18.FTX.C108.4440(1-5)</td>
            <td>'TEXT SUBJECT QUALIFIER' is set to a value of 'SPC' (Service provider's comment). Refer to the description of 'TEXT SUBJECT QUALIFIER' (tag id 4451) in LSR_04_A_001.doc.</td>
        </tr>
        <tr>
            <td>specimen</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>hasMember</td>
            <td></td>
            <td></td>
            <td></td>
            <td>The mechanism for supporting test groups, component tests within test groups and standalone tests in PMIP EDIFACT (NHS003) is described in the definition of Segment Group 18 in LSR_04_A_001.doc.</td>
        </tr>
   </tbody>
</table>

<br>

### UKCore-Observation-Lab (Test Result)

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4ObservationTestResult}}</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>status</td>
            <td>E139</td>
            <td>status of laboratory investigation (result item)</td>
            <td>SG18.STS.C555.9011</td>
            <td></td>
        </tr>
        <tr>
            <td>category</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>code.coding.code</td>
            <td>E108</td>
            <td>measurable quantity attribute</td>
            <td>SG18.INV.C847.9931</td>
            <td></td>
        </tr>
        <tr>
            <td>code.coding.system</td>
            <td>E108</td>
            <td>code list specifying the measurable quantity attribute</td>
            <td>SG18.INV.C847.1131</td>
            <td></td>
        </tr>
        <tr>
            <td>code.coding.display</td>
            <td>E108</td>
            <td>textual representation of the code for measurable quantity attribute</td>
            <td>SG18.INV.C847.9930</td>
            <td></td>
        </tr>
        <tr>
            <td>subject</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>effective[x]</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>issued</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>performer</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>valueQuantity</td>
            <td>E129</td>
            <td>numerical value of a measurement result</td>
            <td>SG18.RSL.C830(1).6314</td>
            <td></td>
        </tr>
        <tr>
            <td>valueQuantity.comparator</td>
            <td>E128</td>
            <td>arithmetic comparator</td>
            <td>SG18.RSL.C830(1).6321</td>
            <td></td>
        </tr>
        <tr>
            <td>valueQuantity.unit</td>
            <td>E130</td>
            <td>unit of measurement result</td>
            <td>SG18.RSL.C848.6410</td>
            <td></td>
        </tr>
        <tr>
            <td>valueString</td>
            <td>E136</td>
            <td>text value of a laboratory investigation result item</td>
            <td>SG18.FTX.C108.4440(1-5)</td>
            <td>'TEXT SUBJECT QUALIFIER' is set to a value of 'RIT' (Text value of a result). Refer to the description of 'TEXT SUBJECT QUALIFIER' (tag id 4451) in LSR_04_A_001.doc.</td>
        </tr>
        <tr>
            <td>dataAbsentReason</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>interpretation</td>
            <td>E137</td>
            <td>deviating result indicator</td>
            <td>SG18.RSL.7857</td>
            <td>Partial mapping to 'RESULT NORMALCY INDICATOR, CODED' (also referred to as 'deviating result indicator'). Refer to the description of 'RESULT NORMALCY INDICATOR, CODED' (tag id 7857) in LSR_04_A_001.doc.</td>
        </tr>
        <tr>
            <td>note</td>
            <td>E141</td>
            <td>comment to laboratory investigation result item</td>
            <td>SG18.FTX.C108.4440(1-5)</td>
            <td>'TEXT SUBJECT QUALIFIER' is set to a value of 'SPC' (Service provider's comment). Refer to the description of 'TEXT SUBJECT QUALIFIER' (tag id 4451) in LSR_04_A_001.doc.</td>
        </tr>
        <tr>
            <td>bodySite</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>method</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>specimen</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>referenceRange.low</td>
            <td>E144</td>
            <td>numerical value of lower reference limit of quantity</td>
            <td>SG20.RND.6162</td>
            <td></td>
        </tr>
        <tr>
            <td>referenceRange.high</td>
            <td>E145</td>
            <td>numerical value of upper reference limit of quantity</td>
            <td>SG20.RND.6152</td>
            <td></td>
        </tr>
        <tr>
            <td>referenceRange.type<br>referenceRange.appliesTo</td>
            <td rowspan="2">E148</td>
            <td rowspan="2">reference population definition</td>
            <td rowspan="2">SG20.FTX.C108.4440(1-5)</td>
            <td rowspan="2">'TEXT SUBJECT QUALIFIER' is set to a value of 'RPD' (Reference population definition). Refer to the description of 'TEXT SUBJECT QUALIFIER' (tag id 4451) in LSR_04_A_001.doc.</td>
        </tr>
        <tr>
        <tr>
            <td>referenceRange.text</td>
            <td>E330</td>
            <td>complex reference range information</td>
            <td>SG18.FTX.C108.4440(1-5)</td>
            <td>'TEXT SUBJECT QUALIFIER' is set to a value of 'CRR' (Complex reference range information). Refer to the description of 'TEXT SUBJECT QUALIFIER' (tag id 4451) in LSR_04_A_001.doc.</td>
        </tr>
        <tr>
            <td>component</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
   </tbody>
</table>

<br>

### UKCore-Patient

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4Patient}}</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier.value</td>
            <td>E202</td>
            <td>official patient identification</td>
            <td>SG7.PNA.C206.7402</td>
            <td></td>
        </tr>
        <tr>
            <td>identifier.value</td>
            <td>E294</td>
            <td>identification of subject of investigation by laboratory service provider</td>
            <td>SG6.RFF.C506.1154</td>
            <td></td>
        </tr>
        <tr>
            <td>name.family</td>
            <td>E313</td>
            <td>family name</td>
            <td>SG7.PNA.C816(1).3836</td>
            <td></td>
        </tr>
        <tr>
            <td>name.given</td>
            <td>E314</td>
            <td>first given name</td>
            <td>SG7.PNA.C816(2).3836</td>
            <td></td>
        </tr>
        <tr>
            <td>name.given</td>
            <td>E315</td>
            <td>middle name</td>
            <td>SG7.PNA.C816(3).3836</td>
            <td></td>
        </tr>
        <tr>
            <td>name.prefix</td>
            <td>E316</td>
            <td>title</td>
            <td>SG7.PNA.C816(4).3836</td>
            <td></td>
        </tr>
        <tr>
            <td>gender</td>
            <td>E217</td>
            <td>patient administrative sex</td>
            <td>SG7.PDI.3917</td>
            <td></td>
        </tr>
        <tr>
            <td>birthDate</td>
            <td>E218</td>
            <td>date and time of birth</td>
            <td>SG7.DTM.C507.2380</td>
            <td></td>
        </tr>
        <tr>
            <td>address.line<br>address.city</td>
            <td>E311</td>
            <td>unstructured address lines</td>
            <td>SG6.ADR.C090.3794(1-5)</td>
            <td></td>
        </tr>
        <tr>
            <td>address.postalCode</td>
            <td>E307</td>
            <td>postal code</td>
            <td>SG6.ADR.3251</td>
            <td></td>
        </tr>
   </tbody>
</table>

<br>

### UKCore-Practitioner (Requester)

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4Practitioner}}</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td>E084</td>
            <td>healthcare registration identification</td>
            <td>SG1.NAD.C082.3039</td>
            <td></td>
        </tr>
        <tr>
            <td>name.family<br>name.given<br>name.prefix</td>
            <td>E092</td>
            <td>person name details</td>
            <td>SG1.NAD.C080.3036(1-2)<td>
            <td></td>
        </tr>  
        <tr>
            <td>telecom</td>
            <td></td>
            <td></td>
            <td><td>
            <td></td>
        </tr>
    </tbody>
</table>

<br>

### UKCore-ServiceRequest-Lab

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4ServiceRequest}}</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td>E152</td>
            <td>identification of laboratory service order by laboratory service requester</td>
            <td>SG4.RFF.C506.1154</td>
            <td>'Reference qualifier' is set to a value of 'ROI' (Order ID by service requester). Refer to the description of 'Reference qualifier' (tag id 1153) in LSR_04_A_001.doc.</td></td>
        </tr>
        <tr>
            <td>identifier</td>
            <td>E153</td>
            <td>identification of laboratory service order by laboratory service provider</td>
            <td>SG4.RFF.C506.1154</td>
            <td>'Reference qualifier' is set to a value of 'SOI' (Order ID by service provider). Refer to the description of 'Reference qualifier' (tag id 1153) in LSR_04_A_001.doc.</td>
        </tr>
        <tr>
            <td>requisition</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>status</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>intent</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>priority</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>code</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>subject</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>authoredOn</td>
            <td>E154</td>
            <td>issue date and time of laboratory service order</td>
            <td>SG4.DTM.C507.2380</td>
            <td></td>
        </tr>
        <tr>
            <td>requester</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>performer</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>reasonCode</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>reasonReference</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>specimen</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td rowspan="2">note</td>
            <td>E045</td>
            <td>type of clinical observation</td>
            <td>SG10.CIN.6810</td>
            <td></td>
        </tr>
        <tr>
            <td>E046</td>
            <td>clinical observation description</td>
            <td>SG10.FTX.C108.4440(1-5)</td>
            <td></td>
        </tr>
   </tbody>
</table>

<br>

### UKCore-Specimen

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4Specimen}}</th>
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="22.5%">FHIR Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="27.5%">Attribute Name</th>
            <th width="17.5%">Message Mapping</th>
            <th width="27.5%">Notes</th> 
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>identifier</td>
            <td>E262</td>
            <td>identification of sample by laboratory service requester</td>
            <td>SG16.RFF.C506.1154</td>
            <td></td>
        </tr>
        <tr>
            <td>accessionIdentifier</td>
            <td>E263</td>
            <td>identification of sample by laboratory service provider</td>
            <td>SG16.RFF.C506.1154</td>
            <td></td>
        </tr>
        <tr>
            <td>status</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>type</td>
            <td>E264</td>
            <td>type of sample</td>
            <td>SG16.SPC.C832.7866</td>
            <td></td>
        </tr>
        <tr>
            <td>subject</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>receivedTime</td>
            <td>E061</td>
            <td>date and time of receipt of collected sample</td>
            <td>SG16.DTM.C507.2380</td>
            <td></td>
        </tr>
        <tr>
            <td>request</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>collection</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>collection.collector</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>collection.collected[x]</td>
            <td>E050</td>
            <td>date and time of sample collection</td>
            <td>SG16.DTM.C507.2380</td>
            <td></td>
        </tr>
        <tr>
            <td>collection.quantity.value</td>
            <td>E055</td>
            <td>numerical value of amount of collected sample</td>
            <td>SG16.QTY.C186.6060</td>
            <td></td>
        </tr>
        <tr>
            <td>collection.quantity.unit</td>
            <td>E056</td>
            <td>unit of amount of collected sample</td>
            <td>SG16.QTY.C848.6410</td>
            <td></td>
        </tr>
        <tr>
            <td>collection.bodySite</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>collection.fastingStatus[x]</td>
            <td>E225</td>
            <td>pre-treatment description</td>
            <td>SG16.SPC.C832.7867</td>
            <td></td>
        </tr>
        <tr>
            <td>condition</td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>note</td>
            <td>E271</td>
            <td>laboratory service provider's comments to sample</td>
            <td>SG16.FTX.C108.4440(1-5)</td>
            <td></td>
        </tr>
    </tbody>
</table>

