### MedicationRequest Repeat Dispensing

| PARENTPRESCRIPTIONID | ITEM_COUNT | REVIEWDATE  | FLAG_REPEAT_DISPENSING   | AUTHORPARTICIPATIONTIME | EXPECTEDUSE |
|--
| 754CB4-E81001-0B9EB8 | 1	| 20201207 | Y | 20200610120600 |28 |


| PRESCRIPTIONID | LINEITEMID | MEDICATIONTRANSCODE | MEDICATIONTRANSDISPLAYNAME | LINEITEMQUANTITYTEXT |    
|--
| 754CB4-E81001-0B9EB8 | A7B86F8D-1D59-FC28-E050-D20AE3A215F0 | 21011811000001100 | Enshake oral powder 96.5g sachets (Flavour Not Specified) | sachet | 
 
| LINEITEMQUANTITYTRANSCODE | LINEITEMQUANTITYTRANSVALUE | DOSAGEINSTRUCTIONSVALUE | ADDITIONALINSTRUCTIONSVALUE | ORIGINALITEMREF |         
|--
| 3318911000001109 | 48 | As Directed	<![CDATA[<medication>Enshake oral powder 96.5g sachets (Flavour Not Specified)</medication><patientInfo> Please call the practice. </patientInfo>]]> | | | 

| PRESCIBERENDORSEMENTCODE | REPEATNUMBER | MAXREPEATS  | CONTROLLED_DRUG_STATUS |
|--
| ACBSAF | 1 | 6 | 0 = No controlled drug status |

<div class="nhsd-!t-margin-bottom-6">
  <ul class="nav nav-tabs" role="tablist">
        <li role="presentation" class="active">
            <a href="#JSON" role="tab" data-toggle="tab">JSON</a>
        </li>
         <li role="presentation">
            <a href="#XML" role="tab" data-toggle="tab">XML</a>
        </li>
        <li role="presentation">
            <a href="#Tree" role="tab" data-toggle="tab">Tree</a>
        </li>
  </ul>
    
  <div class="tab-content snippet">
    <div id="JSON" role="tabpanel" class="tab-pane active">
{{json:MedicationRequest-example}}
    </div>
    <div id="XML" role="tabpanel" class="tab-pane">
{{xml:MedicationRequest-example}}
    </div>
    <div id="Tree" role="tabpanel" class="tab-pane">
{{tree:MedicationRequest-example}}
    </div>
  </div>
</div>
