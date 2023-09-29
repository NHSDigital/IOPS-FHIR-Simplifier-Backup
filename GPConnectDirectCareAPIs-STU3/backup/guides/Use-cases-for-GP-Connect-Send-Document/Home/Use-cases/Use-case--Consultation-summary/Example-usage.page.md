## {{page-title}}

#### GP Practice

##### Appointments

This use case completes the set of capabilities required to fulfil the following workflow:

1. The GP Connect Appointment Management FHIR® API enables booking of a consultation at an alternative organisation.
2. The GP Connect Access Record HTML FHIR® API enables an amenable consultation to take place at the alternative organisation through access to the patient record stored at the patient’s registered practice.
3. After the consultation, GP Connect Send Document enables the details of this consultation to be written back to the registered practice so that the registered practice patient record continues to provide an up-to-date view of care which the patient receives in a GP practice setting.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: The first two steps above use synchronous GP Connect FHIR® API capabilities and an asynchronous messaging approach is taken to facilitate the update made at the registered practice by the final step. GP Connect Appointment Management and GP Connect Access Record HTML are not prerequisites for GP Connect Send Document.
</div>

##### Out of hours

A patient visits an out-of-hours service (not provided by their registered GP practice). After the consultation, GP Connect Send Document enables the details of this consultation to be written back to the registered practice so that the registered practice patient record continues to provide an up-to-date view of care which the patient receives in a GP practice setting.


#### Targeted / specialist services

##### District nursing

A patient under the direct care of a district nurse. Clinically relevant encounters, for example, the start/end of care being provided, should be sent back to the patient’s registered practice using Send Document so that the registered practice patient record continues to provide an up-to-date view of care which the patient receives in a GP practice setting.


**Other potential usage**:

- Specialist cardiac rehabilitation nursing
- Specialist diabetes nursing
- Specialist respiratory practitioners
- Specialist heart failure nurse


#### Universal public health functions

##### School Nursing

A patient receives medical attention while at school. If the encounter contains clinically relevant information, Send Document should be used to send this information back to the patient’s registered practice so that the registered practice patient record continues to provide an up-to-date view of care which the patient receives in a GP practice setting.




</div>



---