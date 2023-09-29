## {{page-title}}

The table below shows the mapping of HL7 v3 Interactions to FHIR API calls, responses and messages. Note the FHIR messages are designed to flow from end to end and are not designed around EPS interactions (i.e. the Prescription Release Respones are very similar to the original Parent Prescription).

### Prescribing Interactions

|  HL7 v3 Interaction | HL7 FHIR Interaction | 
|--
| Parent Prescription - PORX_IN020101UK31 | {{pagelink:prescriptionorder}} | 
| Cancel Request - PORX_IN030101UK32 | {{pagelink:prescriptionordercancel}} | 
| Cancel Response - PORX_IN050101UK31 | {{pagelink:prescriptionordercancel}} | 
| Subsequent Cancel Response - PORX_IN050102UK32 | {{pagelink:PrescriptionCancellationNotification.md}}  | 

<br/>

### Dispensing Interactions

|  HL7 v3 Interaction | HL7 FHIR Interaction |
|--
| Nominated Prescription Release Request - PORX_IN060102UK30 | {{pagelink:prescriptionrelease}} |
| Nominated Prescription Release Response - PORX_IN070101UK31 | {{pagelink:prescriptionrelease}} | 
| Patient Prescription Release Request - PORX_IN132004UK30 | {{pagelink:prescriptionrelease}} |
| Patient Prescription Release Response - PORX_IN070103UK31 | {{pagelink:prescriptionrelease}} |
| Prescription Release Rejection - PORX_IN110101UK30 | {{pagelink:prescriptionrelease}} |
| Dispense Proposal Return - PORX_IN100101UK31 | {{pagelink:ReturningPrescriptionstoEPS.md}} | 
| Dispense Notification - PORX_IN080101UK31 | {{pagelink:DispenseNotification}} | 
| Dispense Notification Update - PORX_IN080101UK31 | {{pagelink:DispenseNotificationUpdate}} | 
| Dispense Withdraw - PORX_IN510101UK31 | {{pagelink:CancelaDispenseNotification.md}} |
| Dispense Claim Information - PORX_IN090101UK31 | {{pagelink:DispenseClaim}} |
| Reimbursement Claim Resubmit - PORX_IN090102UK31 | {{pagelink:DispenseClaimUpdate}} |
