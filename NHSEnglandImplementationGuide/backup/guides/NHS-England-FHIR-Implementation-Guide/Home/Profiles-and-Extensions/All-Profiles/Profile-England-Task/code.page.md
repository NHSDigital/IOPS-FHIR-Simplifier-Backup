## `code`

<b>Definition</b><br>

**e-RS** 

A SNOMED CT procedure code to indicate the action

**EPS**

The SNOMED action codes are complemented with `order delivery` [task-code](https://www.hl7.org/fhir/valueset-task-code.html) which indicates the type of action to be performed against the focal resource. 

For example:

The code `fulfil` used with `182836005 | Review of medication` means a task to review medication.
The code `approve` used with `103742009 | Renewal of prescription` is a task for a clinician to approve the issue of a repeat medication.

---