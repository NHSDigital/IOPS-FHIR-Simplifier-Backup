## {{page-title}}


### Create Patient

#### Use Case



> Following a healthy pregnancy, Mosa gives birth to her new baby, Joshua. Information is captured about Joshua and about the relationship between him and his parents in the hospitals electronic patient records (EPR) system. Leveraging the information in the EPR, a new patient master identity record is created for baby Joshua in NHS England’s Personnel Demographics System (PDS).
> 
> Joshua’s patient master identity in NHS England PDS establishes his unique identity across the English NHS.
> 
> Joshua now has his unique master identifier (NHS Number) for health purposes, which affords care in the English NHS.
> 
> Other local systems and the new GP (Patient Identity Consumer) are informed of this new patient record via Patient Identity Feeds.


#### Process Flow

<plantuml>
@startuml

hide footbox

title Create Patient

actor "Patient Identity Source \n Patient Identity Registry" as source
actor "Patient Identity Consumer" as consumer

source -> source: Create Patient record
source -> consumer: Patient Created event notification
consumer --> source: Acknowledgement


@enduml
</plantuml>

##### Pre-conditions:

Joshua is born at a care facility. The details about his name, his gender, and his parental relationships are known. These are captured in the care facility’s EPR. Since this is a birth and the first time the record is entered in the EMR, no queries are made to search for existing records.

##### Main Flow:

Joshua’s information in the care facility’s EPR is communicated to other systems within the locality via a patient created event notification.

##### Post-conditions:

If the Create message was valid, local systems may create their own patient demographic record. 

When a patient record is created this triggers a Patient Created [Event Message](https://www.enterpriseintegrationpatterns.com/patterns/messaging/EventMessage.html)

### Update Patient 

#### Use Case

> Following a healthy childhood and after completing his schooling, Joshua leaves home to start a new job in a nearby city. As part of starting his new job at his new company, Joshua registers with a local GP.
> 
> Joshua’s identity details are created in the GP’s EPR with his new address and his new mobile phone number. The EPR searches NHS England PDS for Joshua’s master patient identity and then updates NHS England PDS with Joshua’s updated demographic details.

#### Process Flow

<plantuml>
@startuml

hide footbox

title Update Patient

actor "Patient Identity Source \n Patient Identity Registry" as source
actor "Patient Identity Consumer" as consumer

source -> source: Update Patient record
source -> consumer: Patient Updated event notification
consumer --> source: Acknowledgement


@enduml
</plantuml>


##### Pre-conditions:

Joshua has moved to the city and has a new address and mobile phone number. Joshua’s record is retrieved from the EPR and these updated details are captured in the community care facility’s EPR.

##### Main Flow:

Joshua’s information in the care facility’s EPR is communicated to other local systems as an update patient record event notification, this may also make use of a Subscribe-Notify pattern

##### Post-conditions:

If the EPR message was valid, his existing patient record may be updated on the PDS with the new, more up-to-date information that was captured in the community clinic’s EPR.

### Merge Patient

#### Use Case

> Joshua becomes concerned and travels to a different city to visit a Sexual Health clinic to be tested for HIV. He provides inaccurate demographic information at the clinic, who set up a new record for him in their EPR. The EPR communicates this demographic information to NHS England PDS where the NHS Number is not found and so the local demographic record is used instead.
>
> Joshua completes the HIV rapid test, which is positive. A confirmatory test is taken, which must be sent to the regional lab for processing. Both the results of the rapid test and the results of the confirmatory test reference Joshua’s duplicate patient demographic record. The test results are not shared on the Shared Health Record (SHR) as the patient master identity was not found.
> 
> When Joshua returns to the clinic to receive his confirmatory lab results, and after receiving counselling regarding confidentiality rules and the importance of care continuity, Joshua corrects his patient demographic record. The EPR now successfully identifies Joshua’s record on NHS England PDS and this identifies another record for Joshua on the local EPR. The two local records are merged on the EPR and the EPR sends a merge message to all Patient Identity Consumers.
> 
> Note: An unmerge would be handled as an administrative function.
> 
> The various (external) databases that store health information about Joshua have subscribed to patient update transactions on the local EPR. To ensure patient safety for Joshua, these systems ensure that a query using Joshua’s resolved patient master identity would, correctly, return all of the health information associated with him – whether it was originally persisted under his correct (surviving) patient master identity or under the duplicate (subsumed) patient master identity.


#### Process Flow

<plantuml>
@startuml

hide footbox

title Merge Patient

actor "Patient Identity Source \n Patient Identity Registry" as source
actor "Patient Identity Consumer" as consumer

source -> source: Patient Update event received
source -> source: Patient records are identified as duplicate and merged
source -> consumer: Patient Merged event notification
consumer --> source: Acknowledgement

@enduml
</plantuml>

##### Pre-conditions:

Systems that maintain patient information subscribe to the <b>Update Patient</b> event notifications.

##### Main Flow:

A duplicate patient master identity is detected and when the error is found, the duplicate identities are merged on the EPR, and a transaction is executed to merge them on the EPR.

This triggers sending notifications to the health data systems that have subscribed to updates on the EPR/PAS, which include updated information about the patient identities that were merged. Each of these health data systems updates their local health data to reflect the merged patient master identity.

##### Post-conditions:

Following the execution of the triggered merge message, each system that maintains health data about the subject of care has updated this local data to reflect the merge of the two patient identities. The subsumed patient identity is deprecated

When a patient record is merged this triggers a Patient Merge Event Message, this may also make use of a Subscribe-Notify pattern