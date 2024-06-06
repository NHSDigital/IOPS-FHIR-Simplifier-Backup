## {{page-title}}

The status can be used to determine the overall status of dispense request; however, it does not cater for the granularity that prescription tracking software can offer.

It is recommended that the `MedicationDispense.status` is used to indicate the status at a high-level so that integrated systems can determine how to represent this information.


<table>
    <tr>
        <td><b>Completed dispense events</b></td> 
        <td>In situations where the dispense is completed by the pharmacy, then the status of <code>completed</code> should be used.</td>
    </tr>
    <tr>
        <td><b>Declined urgent supply of prescription items</b></td>
        <td>In situations where the dispense is stopped - for example, a request for an urgent supply of medicines for a controlled drug, then the the status of <code>stopped</code> should be used.</td>
    </tr>
</table>


---