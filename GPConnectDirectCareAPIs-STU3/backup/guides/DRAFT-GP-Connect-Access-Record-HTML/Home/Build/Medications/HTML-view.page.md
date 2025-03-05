## {{page-title}}

```html
<div>
   <h1>Medications</h1>
   <div class="gptransfer-banner">
      <p>
         <!-- GP transfer banner -->
      </p>
   </div>
   <div class="content-banner">
      <p>
         <!-- Content banner -->
      </p>
   </div>
   <div>
      <h2>Acute Medication (Last 12 Months)</h2>
      <div class="content-banner">
         <p>
            <!-- Content banner -->
         </p>
      </div>
      <div class="exclusion-banner">
         <p>
            <!-- Exclusion banner -->
         </p>
      </div>
      <table id="med-tab-acu-med">
         <thead>
            <tr>
               <th>Type</th>
               <th>Start Date</th>
               <th>Medication Item</th>
               <th>Dosage Instruction</th>
               <th>Quantity</th>
               <th>Scheduled End Date</th>
               <th>Days Duration</th>
               <th>Additional Information</th>
            </tr>
         </thead>
         <tbody>
            <tr>
               <!-- the <tr>...</tr> element will repeat for each current medication issue-->
               <td>$ medication.type $</td>
               <td class="date-column">$ medication.startDate $</td>
               <td>$ medication.drug $</td>
               <td>$ medication.dosageInstruction $</td>
               <td>$ medication.quantity $</td>
               <td class="date-column">$ medication.scheduledEndDate $</td>
               <td>$ medication.daysDuration $</td>
               <td>$ medication.additionalInformation $</td>
            </tr>
         </tbody>
      </table>
   </div>
   <div>
      <h2>Current Repeat Medication</h2>
      <div class="content-banner">
         <p>
            <!-- Content banner -->
         </p>
      </div>
      <div class="exclusion-banner">
         <p>
            <!-- Exclusion banner -->
         </p>
      </div>
      <table id="med-tab-curr-rep">
         <thead>
            <tr>
               <th>Type</th>
               <th>Start Date</th>
               <th>Medication Item</th>
               <th>Dosage Instruction</th>
               <th>Quantity</th>
               <th>Last Issued Date</th>
               <th>Number of Prescriptions Issued</th>
               <th>Max Issues</th>
               <th>Review Date</th>
               <th>Additional Information</th>
            </tr>
         </thead>
         <tbody>
            <tr>
               <!-- the <tr>...</tr> element will repeat for each current repeat medication-->
               <td>$ medication.type $</td>
               <td class="date-column">$ medication.startDate $</td>
               <td>$ medication.drug $</td>
               <td>$ medication.dosageInstruction $</td>
               <td>$ medication.quantity $</td>
               <td class="date-column">$ medication.lastIssuedDate $</td>
               <td>$ medication.numberIssued $</td>
               <td>$ medication.maxIssues $</td>
               <td class="date-column">$ medication.reviewDate $</td>
               <td>$ medication.additionalInformation $</td>
            </tr>
         </tbody>
      </table>
   </div>
   <div>
      <h2>Discontinued Repeat Medication</h2>
      <div class="content-banner">
         <p>
            <!-- Content banner -->
         </p>
      </div>
      <div class="exclusion-banner">
         <p>
            <!-- Exclusion banner -->
         </p>
      </div>
      <table id="med-tab-dis-rep">
         <thead>
            <tr>
               <th>Type</th>
               <th>Last Issued Date</th>
               <th>Medication Item</th>
               <th>Dosage Instruction</th>
               <th>Quantity</th>
               <th>Discontinued Date</th>
               <th>Discontinuation Reason</th>
               <th>Additional Information</th>
            </tr>
         </thead>
         <tbody>
            <tr>
               <!-- the <tr>...</tr> element will repeat for each discontinued repeat medication-->
               <td>$ medication.type $</td>
               <td class="date-column">$ medication.lastIssuedDate $</td>
               <td>$ medication.drug $</td>
               <td>$ medication.dosageInformation $</td>
               <td>$ medication.quantity $</td>
               <td class="date-column">$ medication.discontinuedDate $</td>
               <td>$ medication.discontinuedReason $</td>
               <td>$ medication.additionalInformation $</td>
            </tr>
         </tbody>
      </table>
   </div>
   <div>
      <h2>All Medication</h2>
      <div class="content-banner">
         <p>
            <!-- Content banner -->
         </p>
      </div>
      <div class="date-banner">
         <p>
            <!-- Date banner -->
         </p>
      </div>
      <div class="exclusion-banner">
         <p>
            <!-- Exclusion banner -->
         </p>
      </div>
      <table id="med-tab-all-sum">
         <thead>
            <tr>
               <th>Type</th>
               <th>Start Date</th>
               <th>Medication Item</th>
               <th>Dosage Instruction</th>
               <th>Quantity</th>
               <th>Last Issued Date</th>
               <th>Number of Prescriptions Issued</th>
               <th>Discontinuation Details</th>
               <th>Additional Information</th>
            </tr>
         </thead>
         <tbody>
            <tr>
               <!-- the <tr>...</tr> element will group and display each distinct medication item-->
               <td colspan="9" class="med-item-column"> <strong>$ medication.drug $</strong></td>
            </tr>
            <tr>
               <!-- the <tr>...</tr> element will repeat for each medication in the group-->
               <td>$ medication.type $</td>
               <td class="date-column">$ medication.startDate $</td>
               <td>$ medication.drug $</td>
               <td>$ medication.dosageInstruction $</td>
               <td>$ medication.quantity $</td>
               <td class="date-column">$ medication.lastIssuedDate $</td>
               <td>$ medication.numberIssued $</td>
               <td>$ medication.discontinuedDetails $</td>
               <td>$ medication.additionalInformation $</td>
            </tr>
         </tbody>
      </table>
   </div>
   <div>
      <h2>All Medication Issues</h2>
      <div class="content-banner">
         <p>
            <!-- Content banner -->
         </p>
      </div>
      <div class="date-banner">
         <p>
            <!-- Date banner -->
         </p>
      </div>
      <div class="exclusion-banner">
         <p>
            <!-- Exclusion banner -->
         </p>
      </div>
      <table id="med-tab-all-iss">
         <thead>
            <tr>
               <th>Type</th>
               <th>Issue Date</th>
               <th>Medication Item</th>
               <th>Dosage Instruction</th>
               <th>Quantity</th>
               <th>Days Duration</th>
               <th>Additional Information</th>
            </tr>
         </thead>
         <tbody>
            <tr>
               <!-- the <tr>...</tr> element will group and display each distinct medication item-->
               <td colspan="7" class="med-item-column"> <strong>$ medication.drug $</strong></td>
            </tr>
            <tr>
               <!-- the <tr>...</tr> element will repeat for each medication in the group-->
               <td>$ medication.type $</td>
               <td class="date-column">$ medication.issueDate $</td>
               <td>$ medication.drug $</td>
               <td>$ medication.dosageInstruction $</td>
               <td>$ medication.quantity $</td>
               <td>$ medication.daysDuration $</td>
               <td>$ medication.additionalInformation $</td>
            </tr>
         </tbody>
      </table>
   </div>
</div>
```