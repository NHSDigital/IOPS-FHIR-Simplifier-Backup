## {{page-title}}

The information below details the additional considerations for the pharmacy first use case in relation to the *CareConnect* profile data mapping and data presentation to the GP system for updating a GP patient record. 

**Profile:** CareConnect-GPC-Encounter-1
<br>

 |Care Connect Field |Conformance |Aditional guidence Note |
 |:----------------- |:---------- |:---------|
 |Outcome of Attendance | <span class="mro-circle required" title="Required"></span> required |Where the information has been recorded on the pharmacy system it should be sent to the GP service|
 |Episode of Care| <span class="mro-circle required" title="Required"></span> required|As per specification|
 |Incoming Referral| <span class="mro-circle required" title="Required"></span> required|As per specification|
 |Reason| <span class="mro-circle required" title="required"></span> required|As per specification|

----
**Profile:** CareConnect-Observation-1

|Care Connect Field |Conformance |Aditional guidence Note |
 |:----------------- |:---------- |:---------|
 |Reference Range|<span class="mro-circle required" title="Required"></span> required|[See Pharmacy Additional Guidance page](https://simplifier.net/guide/gp-connect-update-record/home-examples-community-pharmacy-pharmacy-additional-guidance?version=current) for further information
 
----
**Profile:** CareConnect-GPC-MedicationStatement-1

|Care Connect Field |Conformance |Aditional guidence Note |
 |:----------------- |:---------- |:---------|
|Category | <span class="mro-circle required" title="Required"></span> required|Pharmacy to use a reduced list of the aviliable catalogue codes from the availiable codes|
|Medication Refererence| <span class="mro-circle optional" title="Optional"></span> optional|Linked to another profile in use / summary information useful to pharmacy|
|Effective| <span class="mro-circle required" title="Required"></span> required|From an observation perspective / example the time and date, value or specimen collected|
|Reference Range| <span class="mro-circle required" title="required"></span> required|Not relevant to pharmacy|

----

