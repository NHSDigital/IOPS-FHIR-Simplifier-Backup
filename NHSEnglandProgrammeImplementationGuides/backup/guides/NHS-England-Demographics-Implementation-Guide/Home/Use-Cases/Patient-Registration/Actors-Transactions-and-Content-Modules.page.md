## {{page-title}}


### Use Case

> Following a healthy childhood and after completing his schooling, Joshua leaves home to start a new job in a nearby city. As part of starting his new job at his new company, Joshua registers with a local GP.
>
> The GP receptionist will begin a patient registration process and this will often include completion of a form e.g. GMS1 Form. Once completed details on the form are used to retrieve the NHS England Patient Demographic record from PDS which is used to create a local demographic record. Other details on the form are used to populate the local EPR record (e.g. weight, smoking status, etc)


### Process Flow



<plantuml>

@startuml

hide footbox

title Patient Registration

actor "Patient" as patient
actor "Patient Identity Source" as source

source -> patient: Patient is asked to complete **Patient Registration** form [PCC-UK-2]
opt
note over patient: May use [PCC-UK-3] to retrieve **Patient Proxy Request** Form Definition
end
opt
  patient -> patient: **Patient Registration** form can be pre-populated
end
patient -> patient : Patient completes  **Patient Registration** form
patient -> source: Send Completed **Patient Registration** form [PCC-ENG-1]
source --> patient: Acknowledgement
source -> source: Create patient
opt
source -> source: Extract health record\ndata from the form \nand add to the patients record
end
@enduml

</plantuml>


#### Pre-conditions:

GP Receptionist has access to the EPR/PAS. Receptionist is unable to find the patient on the EPR/PAS. 

#### Main Flow:

Receptionist initiates the registration process and patient completes the registration form providing the necessary personal information, which the receptionist then uses to retrieve the PDS record. If a matching record is found, then the data is used to create a local EPR.

#### Post-conditions:

New patient's registration process is successfully completed. <b>Create Patient</b> is likely to be triggered.
