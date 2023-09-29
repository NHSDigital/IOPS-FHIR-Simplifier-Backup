## Design

- <a href="#actors">Actors</a>
- <a href="#actorsandtransactions">Actors and Transactions</a>
  - <a href="#workflow">Prescribing and Dispensing Workflow</a>
  - <a href="#epsqueryapi">EPS Query API</a>
  - <a href="#otherservices">Other Services or API's</a>
- <a href="#references">References</a>

The Electronic Prescription Service (EPS) supports the community medication prescribing and dispensing business processes using the HL7 FHIR R4 standard.

In general, the medication business process consists of four distinct processes, which must be connected through interactions that transfer information and/or guide the workflow. The following figure shows this flow (**Note:** The scope of EPS **does not** include Medication Administration):

{{render:medication-process}}

The use of medicines to treat a patient generally follows the diagram above. The medication is prescribed by the prescriber, it is dispensed by the dispenser and it is then taken by the patient.

Each part of this process is supported by different FHIR resources and the overall current usage of the drugs is supported by Medication Statement`.

| FHIR Resource | Description |
|--
| `MedicationRequest` | An order for both supply of the medication and the instructions for administration of the medicine to a patient. |
| `MedicationDispense` | Provision of a supply of a medication with the intention that it is subsequently consumed by a patient (usually in response to a prescription). |
| `MedicationAdministration` |When a patient actually consumes a medicine, or it is otherwise administered to them. |
| `MedicationStatement` | This is a record of medication being taken by a patient, or that the medication has been given to a patient where the record is the result of a report from the patient, or another clinician. A medication statement is not a part of the prescribe->dispense->administer sequence but is a report that such a sequence (or at least a part of it) did take place resulting in a belief that the patient has received a particular medication. |


<br>

<a name="actors"></a>
### Actors

EPS involves several key actors:

| Actor | Description |
|--
| Workflow Manager (EPS) | The role of this actor consists in providing the business logic for status management and other purposes. There is no human actor behind this system actor. |
| Prescription Placer (Prescriber) | The main role of this actor consists in placing the prescription (initial or modified in case of a substitution of invalidation, for example). It sends the cancellation of the prescription or its discontinuation. The human actor behind this system actor will be a clinician qualified to be a prescriber of medication. |
| Medication Dispenser (Dispenser) | This actor is responsible for the process of dispensing medication to the patient, fulfilling the prescription. It produces information on the actual medication dispensed to the patient. The human actor behind this system actor will be a pharmacist or a pharmacy dispensing technician. |
| Reimbursement Payer (Reimbursement) | This actor is responsible for prescription reimbursement; the paying of professional services fees and/or the cost of the medication. For community dispensed prescriptions this is the NHS Business Services Authority. |
| Patient | This actor is the subject of medication treatment, the patient. | 
| Practitioner | This actor is a person who is directly or indirectly involved in the provisioning of healthcare to the patient (not limited to community pharmacy workflow). The human actor behind this system actor may be a clinician or a member of clinical support staff. | 

<br>

<a name="actorsandtransactions"></a>
### Actors and Transactions

<a name="workflow"></a>
#### Prescribing and Dispensing Workflow

{{pagelink:PrescribingandDispensingWorkflow.md }} - Interactions which facilitate and coordinate the delivery of medication treatment between organisations and systems. This is based on [FHIR Workflow](https://www.hl7.org/fhir/workflow.html) 

<table class="regular" style="width:100%">
 <thead>
   <tr>
     <th data-no-sort >Area</th>
     <th data-no-sort >Transaction</th>
     <th data-no-sort >EPS</th>
     <th data-no-sort >Prescriber</th>
     <th data-no-sort >Dispenser</th>
     <th data-no-sort >Reimbursement</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
{{pagelink:PrescriptionOrdering}} 
    </td>
    <td>
   {{pagelink:PrescriptionSigning.md}}
    </td>
    <td>
&#10004;
    </td>
     <td>
&#10004;
    </td>
    <td>
    </td>
    <td>
    </td>
   </tr>
    <tr>
    <td>
    </td>
    <td>
   {{pagelink:PrescriptionOrder.md}}
    </td>
    <td>
&#10004;
    </td>    
     <td>
&#10004;
    </td>
    <td>
    </td>
    <td>
    </td>
   </tr>
     <tr>
    <td>
    </td>
    <td>
   {{pagelink:PrescriptionOrderCancel.md}}
    </td>
    <td>
&#10004;
    </td>
     <td>
&#10004;
    </td>
    <td>
    </td>
    <td>
    </td>
   </tr>
     <tr>
    <td>
{{pagelink:prescriptiondownloadanddispensing}}
    </td>
    <td>
   {{pagelink:PrescriptionRelease.md}}
    </td>
    <td>
&#10004;
    </td>
     <td>
   </td>
    <td>
&#10004;
    </td>
    <td>
    </td>
   </tr>
    <tr>
    <td>
    </td>
    <td>
   {{pagelink:DispenseNotification.md}}
    </td>
    <td>
&#10004;
    </td>
     <td>
    </td>
    <td>
&#10004;
    </td>
    <td>
    </td>
   </tr>
    <tr>
    <td>
    </td>
    <td>
   {{pagelink:DispenseNotificationUpdate.md}}
    </td>
    <td>
&#10004;
    </td>
     <td>
    </td>
    <td>
&#10004;
    </td>
    <td>
    </td>
   </tr>
     <tr>
    <td>
    </td>
    <td>
   {{pagelink:returningprescriptionstoEPS.md}}
    </td>
    <td>
&#10004;
    </td>
     <td>
    </td>
    <td>
    &#10004;
    </td>
    <td>
    </td>
   </tr>
    <tr>
    <td>
    </td>
    <td>
   {{pagelink:canceladispensenotification.md}}
    </td>
    <td>
&#10004;
    </td>
     <td>
    </td>
    <td>
&#10004;
    </td>
    <td>
    </td>
   </tr>
     <tr>
    <td>
{{pagelink:PrescriptionClaiming}} 
    </td>
    <td>
   {{pagelink:DispenseClaim.md}}
    </td>
    <td>
&#10004;
    </td>
     <td>
    </td>
    <td>
&#10004;
    </td>
    <td>
&#10004;
    </td>
   </tr>
    <tr>
    <td>
    </td>
    <td>
   {{pagelink:DispenseClaimUpdate.md}}
    </td>
    <td>
&#10004;
    </td>
     <td>
    </td>
    <td>
&#10004;
    </td>
    <td>
&#10004;
    </td>
   </tr>
    <tr>
    <td>
{{pagelink:PrescriptionManagement}} 
    </td>
    <td>
    </td>
    <td>
&#10004;
    </td>
     <td>
&#10004;
    </td>
    <td>
    &#10004;
    </td>
    <td>
    </td>
   </tr>
  </tbody>
</table>

<br>

<a name="epsequeryqpi"></a>
#### EPS Query API

{{pagelink:EPSQueryAPI}} - Enables the querying of medication treatment and workflow information stored with EPS. This is based on [FHIR RESTful](https://www.hl7.org/fhir/http.html)

Covering the querying of **MedicationRequest**, **MedicationDispense** and **Task** (overall prescription status)
This API may also be used for patient facing services and querying of patient medication data. 

<br>

<a name="otherservices"></a>
### Other Services

{{pagelink:OtherServices}} | Services or APIs which are used with with EPS.


<br>

<a name="references"></a>
#### References

- [IHE Community Medication Prescription and Dispense (CMPD)](https://www.ihe.net/uploadedFiles/Documents/Pharmacy/IHE_Pharmacy_Suppl_CMPD.pdf)
- [IHE Hospital Medication Workflow (HMW)](https://www.ihe.net/uploadedFiles/Documents/Pharmacy/IHE_Pharmacy_Suppl_HMW.pdf)