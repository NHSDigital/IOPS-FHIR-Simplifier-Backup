## `reasonCode`

<b>Definition</b><br>

In FHIR Task these types of workflow would be represented via **reasonCode** and/or **reasonReference**

For medication this is probably SNOMED CT based using codes under the SNOMED CT 182832007 Medication management and includes codes such as:

| SNOMED CT | Display |
|--|--|
| 33633005 | Prescription of drug |
| 373784005 | Dispensing medication |

<br/>

For referral management

| SNOMED CT | Display |
|--|--|
| <a href="https://ontoserver.csiro.au/shrimp/?concept=3457005&version=http%3A%2F%2Fsnomed.info%2Fsct%2F83821000000107%2Fversion%2F20211124&valueset=http%3A%2F%2Fsnomed.info%2Fsct%2F83821000000107%3Ffhir_vs&fhir=https%3A%2F%2Fontology.nhs.uk%2Fauthoring%2Ffhir">3457005</a> | Patient Referral |
| <a href="https://ontoserver.csiro.au/shrimp/?concept=185499000&version=http%3A%2F%2Fsnomed.info%2Fsct%2F83821000000107%2Fversion%2F20211124&valueset=http%3A%2F%2Fsnomed.info%2Fsct%2F83821000000107%3Ffhir_vs&fhir=https%3A%2F%2Fontology.nhs.uk%2Fauthoring%2Ffhir">185499000</a>| Expedite appointment |

---