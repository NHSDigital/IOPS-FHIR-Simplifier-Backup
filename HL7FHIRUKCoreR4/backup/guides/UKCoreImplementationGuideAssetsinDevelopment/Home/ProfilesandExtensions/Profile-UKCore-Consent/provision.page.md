## <code>{{page-title}}</code>

<code>provision.actor.reference</code>

The resource being referenced SHOULD conform to one of the following:
- {{pagelink:Profile-CareTeam}}
- {{pagelink:Profile-Device}}
- [Group Resource](https://hl7.org/fhir/R4/group.html)
- [Profile UKCore-Organization](https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Organization)
- [Profile UKCore-Patient](https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Patient)
- [Profile UKCore-Practitioner](https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-Practitioner)
- [Profile UKCore-PractitionerRole](https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-PractitionerRole)
- [Profile UKCore-RelatedPerson](https://simplifier.net/guide/UK-Core-Implementation-Guide-STU3-Sequence/Home/ProfilesandExtensions/Profile-UKCore-RelatedPerson)

<code>provision.data.reference</code>

Where a UK Core profile exists the resource being referenced SHOULD conform to the profile.

<code>provision.code</code>

This element has a binding to {{pagelink:ValueSet-UKCore-ConsentException}}.

---
