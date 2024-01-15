## <code>{{page-title}}</code>

### `Specimen.collection.collector`

The resource being referenced SHALL conform to one of the following:
- {{pagelink:Profile-Practitioner}}
- {{pagelink:Profile-PractitionerRole}}

### `Specimen.collection.bodySite`

If `Specimen.collection.bodySite.coding` and {{pagelink:Extension-UKCore-BodySiteReference}} are both are present, they are expected to be consistent with each other - e.g. the concept is to a code for headache, and the resource reference describes a headache.

---
