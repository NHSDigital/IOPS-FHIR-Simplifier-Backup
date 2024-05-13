## {{page-title}}


### Use Case



> Mosa is pregnant and visits the local maternity ward for the first time.
>
> The maternity nurse needs to register the patient; in doing so, it is desired to record the patient’s demographic data in the Electronic Patient Record (EPR). The hospital is connected to a NHS England Personnel Demographic Service (PDS). The nurse issues a patient demographic query request to PDS acting as a Patient Identity Source, with some basic patient demographics data as search criteria.
>
> In the returned patient list, she picks an appropriate record for the patient and this is used to create a local patient demographic record in the EPR. Other local systems (Patient Identity Consumer) are informed of this new patient record via Patient Identity Feeds.
>
> Note: PDS may be replaced with a local Patient Administration System (PAS) or regional Master Patient Index (MPI) systems. The use of PDS is often a background interaction.

---

### Process Flow

<plantuml>
@startuml

hide footbox

title Find Patient

actor "Patient Demographics Consumer" as consumer
actor "Patient Identity Source" as source

consumer -> source: Patient Demographic Query
source --> consumer: Matching Patient Demographics


@enduml
</plantuml>

#### Pre-conditions:

The maternity nurse has access to an EPR/PAS and has the valid authorisaton to retrieve the patient's details and has details of the patient's required demographic data.

####  Main Flow:

The maternity nurse initiates a search query within EPR/PAS which then retrieves her demographic data. If multiple matches are found, the maternity nurse will select the desired record from the list.

#### Post-conditions:

The patient identity (NHS Number or MRN) is used to access API's and systems.

