## Dispense - Owings and Partial Dispensing


<br>

### Dispense Notifications 


{{render:dispense-notification}}



#### 1st Dispensing Event – Prescription Status: “With Dispenser – Active”

This is the first dispense notification sent by the dispenser using the FHIR Operation {{pagelink:process-message-duplicate-3}} (`POST /$process-message`)

{{pagelink:stdispenseevent-partial}}

| Medication ID (SNOMED) | Medication Name | Dispensed Quantity | Item Status |
|--
| 1858411000001101 | Paracetamol 500mg soluble tablets (Unichem Plc) 60 t ablets | 60 | 0003 (Partial) |
| 3416211000001106 | Salbutamol 100micrograms/dose inhaler (Sandoz Ltd) 200  dose | 200 | 0001 (Dispensed) |

<br>


#### 2nd Dispensing Event – Prescription Status: “With Dispenser – Active”

This is the second dispense notification sent by the dispenser using the FHIR Operation {{pagelink:process-message-duplicate-3}}

The second drug has not been dispensed but it currently a requirement that *empty* MedicationDispense is included in the `dispense-notification` message. This *empty* uses the prescribed drug dm+d code and the following elements are not present

- performer
- quantity
- daysSupply
- whenPrepared
- dosageInstruction 

{{pagelink:nddispenseevent-partial}}

| Medication ID (SNOMED) | Medication Name | Dispensed Quantity | Item Status|
|--
| 915611000001105 |Paracetamol 500mg soluble tablets (AAH Pharmaceuticals Ltd) 24 tablets | 24 | 0003 (Partial) |
| 35936511000001108 | Salbutamol 100micrograms/dose inhaler | 0 | 0001 (Dispensed) |


<br>


#### 3rd Dispensing Event – Prescription Status: “Dispensed”

This is the final dispense notification sent by the dispenser using the FHIR Operation {{pagelink:process-message-duplicate-3}}

{{pagelink:rddispenseevent-completed}}

| Medication ID (SNOMED) | Medication Name | Dispensed Quantity | Item Status |
|--
| 2274211000001101 | Paracetamol 500mg soluble tablets (Kent Pharmaceuticals) 16 tablets | 16 | 0001 (Dispensed) |
| 35936511000001108 | Salbutamol 100micrograms/dose inhaler  | 0 | 0001 (Dispensed) |



