## `healthcareService`

<b>Definition:</b>

**SHOULD** be provided for a practitioner in secondary care and will be a reference to clinic or service. This referenced resource or the identifier reference **SHOULD** contain a ODS/ANANA identifier. In secondary care Electronic Prescription Service (EPS) this will also be called **prescribing cost centre**. This is used for reimbursements from NHS BSA. In secondary care the healthchare/service cost centre may also be the ODS code for the clinic.

### healthcareService Resource reference

An *identifier reference* **MUST** be included. For secondary care organisations this will be the ODS/ANANA Cost Centre code given to a clinic.

Optionally *Resource reference* can be provided. This is required in the current version of EPS but this will be changed to supporting the *identifier reference* only.

---

