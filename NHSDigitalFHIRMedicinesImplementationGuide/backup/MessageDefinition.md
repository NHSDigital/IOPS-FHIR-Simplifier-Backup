## MessageDefinition


The following FHIR Event messages are defined in this implementation Guide.



<table class="regular" style="width:100%">
 <thead>
   <tr>
     <th data-no-sort width="30%">Prescription Messages</th>
     <th data-no-sort width="70%">Description</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
{{pagelink:prescription-order}}
    </td>
    <td>
A message to order or request for both supply of the medication and the instructions for administration of the medication to a patient.
    </td>
   </tr>
   <tr>
    <td>
{{pagelink:prescription-order-update}}
    </td>
    <td>
A message to request alteration of a prescription-order. This may alter or cancel individial MedicationRequests
    </td>
   </tr>
    <tr>
    <td>
{{pagelink:prescription-order-response}}
    </td>
    <td>
A response message to the update (cancel) request
    </td>
   </tr>
   </tbody>
</table>

<br>

<table class="regular" style="width:100%">
 <thead>
   <tr>
     <th data-no-sort width="30%">Dispense Messages</th>
     <th data-no-sort width="70%">Description</th>
   </tr>
 </thead>
 <tbody>
   <tr>
    <td>
{{pagelink:dispense-notification}}
    </td>
    <td>
A dispensing notification event message
    </td>
   </tr>
   <tr>
    <td>
{{pagelink:dispense-notification-update}}
    </td>
    <td>
A replacement of a dispensing notification message
    </td>
   </tr>
   </tbody>
</table>

<br>

