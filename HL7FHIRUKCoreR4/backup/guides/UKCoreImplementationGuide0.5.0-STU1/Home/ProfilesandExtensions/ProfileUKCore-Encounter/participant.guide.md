## <code>{{page-title}}</code>

List of participants involved in the encounter. This should included the role of participant in encounter using the following values which may be extended.

<table id="assets">
<tr>
<th >Code</th>
<th>System</th>	
<th>Display</th>
<th>Definition</th>
</tr>
<tr>
<td>ADM</td>	
<td>http://terminology.hl7.org/CodeSystem/v3-ParticipationType</td>	
<td>admitter</td>	
<td>The practitioner who is responsible for admitting a patient to a patient encounter.</td>
</tr>
<tr>
<td>ATND</td>	
<td>http://terminology.hl7.org/CodeSystem/v3-ParticipationType</td>
<td>attender</td>	
<td>The practitioner that has responsibility for overseeing a patient's care during a patient encounter.</td>
</tr>
<tr>
<td>CALLBCK</td>	
<td>http://terminology.hl7.org/CodeSystem/v3-ParticipationType</td>	
<td>callback contact</td>	
<td>A person or organization who should be contacted for follow-up questions about the act in place of the author.</td>
</tr>
<tr>
<td>CON</td>	
<td>http://terminology.hl7.org/CodeSystem/v3-ParticipationType</td>	
<td>consultant</td>
<td>An advisor participating in the service by performing evaluations and making recommendations.</td>
</tr>
<tr>
<td>DIS</td>	
<td>http://terminology.hl7.org/CodeSystem/v3-ParticipationType</td>	
<td>discharger</td>	
<td>The practitioner who is responsible for the discharge of a patient from a patient encounter.</td>
</tr>
<tr>
<td>ESC</td>	
<td>http://terminology.hl7.org/CodeSystem/v3-ParticipationType</td>	
<td>escort</td>	
<td>Only with Transportation services. A person who escorts the patient.</td>
</tr>
<tr>
<td>REF</td>	
<td>http://terminology.hl7.org/CodeSystem/v3-ParticipationType</td>	
<td>referrer</td>	
<td>A person having referred the subject of the service to the performer (referring physician). Typically, a referring physician will receive a report.</td>
</tr>
<tr>
<td>SPRF</td>	
<td>http://terminology.hl7.org/CodeSystem/v3-ParticipationType</td>	
<td>secondary performer</td>	
<td>A person assisting in an act through his substantial presence and involvement This includes: assistants, technicians, associates, or whatever the job titles may be.</td>
</tr>
<tr>
<td>PPRF</td>	
<td>http://terminology.hl7.org/CodeSystem/v3-ParticipationType</td>	
<td>primary performer</td>	
<td>The principal or primary performer of the act.</td>
</tr>
<tr>
<td>PART</td>	
<td>http://terminology.hl7.org/CodeSystem/v3-ParticipationType</td>	
<td>Participation</td>	
<td>Indicates that the target of the participation is involved in some manner in the act, but does not qualify how.</td>
</tr>
<tr>
<td>translator</td>	
<td>http://terminology.hl7.org/CodeSystem/participant-type</td>	
<td>Translator</td>	
<td>A translator who is facilitating communication with the patient during the encounter.</td>
</tr>
<tr>
<td>emergency</td>	
<td>http://terminology.hl7.org/CodeSystem/participant-type</td>	
<td>Emergency</td>	
<td>A person to be contacted in case of an emergency during the encounter.</td>
</tr>
</table>

The `participant.individual` element should use a reference to a resource which conforms to one of the following:

- {{pagelink:Profile-Practitioner-96448d2b-cd33-42cb-b1db-f48ae31db401}}
- {{pagelink:Profile-PractitionerRole-91e0c0ae-8b79-41de-b8e1-4eeb30ab2565}}
- {{pagelink:Profile-RelatedPerson-c856ea45-d917-41ac-8d9d-7dcd72d25b02}}


---


