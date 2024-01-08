## {{page-title}}

There are occasions when information within a patient’s record is not suitable or desirable to be disclosed to them. This might be for a temporary period of time such as test results that either should or must be disclosed by their primary healthcare professional before they can be discussed with the patient, or it might be information that could cause the patient psychological harm and the healthcare professional has deemed a risk to patient’s emotional well-being should it be discussed with them.

Alongside information not suitable for patient disclosure there is another category of information, classified as sensitive and confidential. This is information that the primary healthcare professional has deemed to not be suitable for disclosure to other healthcare professionals. Currently, this information is only returned in a call made to the [migrate a patient’s record](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_migrate_patient_record.html) API when the parameter `includeSensitiveInformation` is set to `true`. The inclusion of security labels does not change this behaviour i.e. if information was not going to be output previously due to sensitivity or confidentiality reasons, this should still be the case. And for information that was previously output this should continue to be output, just now it should be output according to the guidance below and with a security label, if appropriate.

Any resource, with the exception of {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-List-1}}, {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--GPConnect-StructuredRecord-Bundle-1}} and {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--Binary}} that contains information that is not to be disclosed to the patient **MAY** be marked with the `NOPAT` [security label](https://hl7.org/fhir/stu3/resource.html#security-labels) within the [Resource Metadata](https://hl7.org/fhir/stu3/resource.html#Meta). [`NOPAT`](https://hl7.org/fhir/stu3/v3/ActCode/cs.html#v3-ActCode-NOPAT) is a code within the [ActCode Code System](https://hl7.org/fhir/stu3/v3/ActCode/cs.html) and signifies the information should not be disclosed to the patient, family or caregivers.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: When a supplier wishes to communicate that information within a resource is not suitable for a patient, it is this label that <b>MUST</b> be used.
</div>

The label should be applied to the [Meta.security](http://hl7.org/fhir/stu3/resource-definitions.html#Meta.security) element as follows:

```json
{
  "meta":{
    "security":[
      {
        "system":"http://hl7.org/fhir/v3/ActCode",
        "code":"NOPAT",
        "display":"no disclosure to patient, family or caregivers without attending provider's authorization"
      }
    ]
  }
}
```

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Important</b>: The absence of a label has no special meaning i.e. it doesn’t mean the information within is suitable for a patient. The information may have been reviewed and deemed suitable for a patient, however, it may not have been reviewed at all. Therefore, where no label is present, information disclosure to the patient must be handled in the normal way and is ultimately the responsibility of the healthcare professional.
</div>

For any resource carrying information that has been deemed to not be suitable to be disclosed to the patient:

- in a response to [retrieve a patient’s record](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_retrieve_patient_record.html):
    - Providers **MAY** include the `NOPAT` security label for all applicable resources
    - Consumers **MAY** utilise the information to display a message to the healthcare professional that the information is not to be disclosed to the patient
- in a response to [migrate a patient’s record](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_migrate_patient_record.html):
    - Providers **MUST** include the `NOPAT` security label for all applicable resources
    - Consumers **MUST** record the `NOPAT` security label against any resources as returned within the response from the Provider

It is anticipated additional labels will be introduced in the future and as such the existence of the label is not enough to consider the information is not suitable for patient disclosure, the security label must be for `NOPAT`.

### Documents not to be disclosed to a patient

There are two APIs available to retrieve a patient’s documents, [retrieve a document](https://developer.nhs.uk/apis/gpconnect-1-6-0/access_documents_development_retrieve_patient_documents.html) and [migrate a document](https://developer.nhs.uk/apis/gpconnect-1-6-0/access_documents_development_migrate_patient_documents.html). Both APIs return a {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--Binary}} resource that can not have security labels applied. However, prior to calling either API a search is performed for the patient’s documents, retrieve a document uses [search for a patient’s documents](https://developer.nhs.uk/apis/gpconnect-1-6-0/access_documents_development_search_patient_documents.html) and migrate a document uses [migrate a patient’s record](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_migrate_patient_record.html). Within the responses to these calls is a list of {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-DocumentReference-1}} that are able to have security labels applied. Security labels can be applied to the DocumentReference resource (through the `meta.security` element, as described above), and in doing so the existence of the document has been deemed to not be suitable for the patient to know. Or, the document might not be suitable for a patient e.g. a test result that needs discussion first. In this scenario the reference to the document needs to have the security label applied. This is done through the `DocumentReference.securityLabel` element. It **MUST** be populated as follows:

```json
{
  "securityLabel":[
    {
      "coding": [
        {
          "system":"http://hl7.org/fhir/v3/ActCode",
          "code":"NOPAT",
          "display":"no disclosure to patient, family or caregivers without attending provider's authorization"
        }
      ]
    }
  ]
}
```

Where applicable, Providers **MUST** ensure DocumentReferences contain the appropriate `NOPAT` security label either on the DocumentReference resource (in the `meta.security` element), the `securityLabel` element or both. Consumers **MUST** honour and store this information against the documents returned in the search list.

### Other security labels

Other security labels **MAY** be included, however, `NOPAT` labels **MUST** be used in the way described above.