## {{page-title}}

dm+d is preferred within `Medication*.medicationCodeableConcept` rather than a reference to a `Medication` FHIR resource within `medicationReference`, since dm+d contains a wealth of information about medications in general - and many of dm+d are interchangeable (e.g., the same as) SNOMED codes.

There are some instances where dm+d cannot be fully be utilised, for example, when describing infusions; however, since infusions are primarily a secondary-care concept, it is not expected to be a challenge for Community Pharmacy use-cases that this specification supports.

More information on dm+d can be found using the link below.

https://www.nhsbsa.nhs.uk/pharmacies-gp-practices-and-appliance-contractors/dictionary-medicines-and-devices-dmd

---