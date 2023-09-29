## Element: `subject` <span class="mro-circle mandatory" title="Mandatory"></span>

Normally this is provided by reference to a CareConnect Patient which **must** include the following if available:

- `Patient.Patient.identifier:nhsNumber`
- `Patient.Patient.name`
- `Patient.birthDate`

Some use cases do not require the full detail provided by a reference to a CareConnect Patient when this is the case the patient may be identified using the child elements of `MedicationStatement.subject`. 

For example:

- Name
- NHS Number
Hospital Number.

Developers should ensure that in the context of use that clinical safety issues are not created where multiple identifiers are not provided.

---