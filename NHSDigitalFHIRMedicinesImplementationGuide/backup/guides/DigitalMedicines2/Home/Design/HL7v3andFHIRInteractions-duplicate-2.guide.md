## {{page-title}}

The table below shows the mapping of HL7 v3 Interactions to FHIR API calls, responses and messages. Note the FHIR messages are designed to flow from end to end and are not designed around EPS interactions (i.e. the Prescription Release Respones are very similar to the original Parent Prescription).

### Prescribing Interactions

|  HL7 v3 Interaction | HL7 FHIR Interaction | 
|--
| Parent Prescription - PORX_IN020101UK31 | {{pagelink:prescriptionorder-duplicate-5}} | 
| Cancel Request - PORX_IN030101UK32 | {{pagelink:prescriptionordercancel-duplicate-2}} | 
| Cancel Response - PORX_IN050101UK31 | {{pagelink:prescriptionordercancel-duplicate-2}} | 
| Subsequent Cancel Response - PORX_IN050102UK32 | See Prescription Tracker API  | 

<br/>

### Dispensing Interactions

|  HL7 v3 Interaction | HL7 FHIR Interaction |
|--
| Nominated Prescription Release Request - PORX_IN060102UK30 | {{pagelink:prescriptionrelease-duplicate-2}} |
| Nominated Prescription Release Response - PORX_IN070101UK31 | {{pagelink:prescriptionrelease-duplicate-2}} | 
| Patient Prescription Release Request - PORX_IN132004UK30 | {{pagelink:prescriptionrelease-duplicate-2}} |
| Patient Prescription Release Response - PORX_IN070103UK31 | {{pagelink:prescriptionrelease-duplicate-2}} |
| Prescription Release Rejection - PORX_IN110101UK30 | {{pagelink:prescriptionrelease-duplicate-2}} |
| Dispense Proposal Return - PORX_IN100101UK31 | {{pagelink:ReturningPrescriptionstoEPS-duplicate-3}} | 
| Dispense Notification - PORX_IN080101UK31 | {{pagelink:DispenseNotification-duplicate-2}} | 
| Dispense Notification Update - PORX_IN080101UK31 | {{pagelink:DispenseNotificationUpdate-duplicate-2}} | 
| Dispense Withdraw - PORX_IN510101UK31 | {{pagelink:CancelaDispenseNotification-duplicate-2}} |
| Dispense Claim Information - PORX_IN090101UK31 | {{pagelink:DispenseClaim-duplicate-2}} |
| Reimbursement Claim Resubmit - PORX_IN090102UK31 | {{pagelink:DispenseClaimUpdate-duplicate-2}} |
