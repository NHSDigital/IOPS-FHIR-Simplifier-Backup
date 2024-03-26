## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional

<h5><ins>Guidance</ins></h5>

References prior prescription authorisation.

May be used, for example, to reference prior authorisation where prescription is re-authorised or where amendments have been made. May reference the previous authorisation before the amendment.

The published FHIR specifications described this element is slightly different ways in different parts of the FHIR specification:

1. A link to a resource representing an earlier order related order or prescription.
2. An order or prescription that is being replaced.

The following guidance applies to each use case.

<ins>Linking to an earlier request</ins>

A medication request that is a re-supply medication request based on a previous request referenced within `priorPrescription`. This would allow both the ePMA and pharmacy systems to logically link requests and add verification checks to flag any differences to the user.

<ins>Linking to an order that is being replaced</ins>

The medication request being replaced will be referenced within `priorPrescription`. It would be expected that the referenced resource would be updated with a status of `cancelled`, `entered-in-error` or `stopped`.

This will allow both the ePMA and pharmacy systems to make it clear to the human user that one medication request replaces another.


<h5><ins>Example</ins></h5>

```xml
<priorPrescription>
    <reference value="medicationrequest-00578231" />
</priorPrescription>
```

---