## {{page-title}}

- the `relatesTo` element within `CareConnect-GPC-Composition-1` **MUST** be populated with the code of `replaces` and the `targetIdentifier` containing the ID of the payload it is replacing
- the version **SHOULD** be included in the `CareConnect-GPC-Composition-1` resource in `meta.versionId`
- replacements **MAY** be done more than once, and the new document always refers to the previous document
- multiple replacements **SHOULD** be avoided where possible due to complexity of maintaining the audit trail
- replacement payloads **SHOULD** be sent within 24 hours of the original payload
- the sender may wish to contact the receiving practice to notify them of the change

---