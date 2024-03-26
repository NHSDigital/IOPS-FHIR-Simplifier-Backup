---
topic: DataMapping
---
## Data Mapping

### UKCore-DiagnosticReport-Lab

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4DiagnosticReport}}</th>   
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="20%">Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="30%">Attribute Name</th>
            <th width="10%">Message Mapping</th>
            <th width="30%">Notes</th> 
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
            <td>EDIFACT 'STATUS EVENT' (status of laboratory service report) is always set to 'UN' (Unspecified). Refer to the description of 'STATUS EVENT' (tag id C555) in LSR_04_A_001.doc.</td>
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

### UKCore-Observation-Group-Lab (Test Group)

<table class="regular">
    <thead>
        <tr>
            <th colspan="1">{{pagelink:R4ObservationTestGroup}}</th>   
            <th colspan="4">PMIP EDIFACT (NHS003) Mapping</th>
        </tr>
        <tr>
            <th width="20%">Element Name</th>
            <th width="10%">Attribute Id</th>
            <th width="30%">Attribute Name</th>
            <th width="10%">Message Mapping</th>
            <th width="30%">Notes</th> 
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
            <td rowspan="2">code</td>
            <td rowspan="2">E108</td>
            <td rowspan="2">measurable quantity attribute</td>
            <td>SG18.INV.C847.9931</td>
            <td></td>
        </tr>
        <tr>
            <td>SG18.INV.C847.9930</td>
            <td></td>
        </tr>
        <tr>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
            <td></td>
        </tr>
   </tbody>
</table>


