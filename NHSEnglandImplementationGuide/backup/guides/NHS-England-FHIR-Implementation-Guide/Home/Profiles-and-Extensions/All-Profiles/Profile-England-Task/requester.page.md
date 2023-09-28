## `requester`

<b>Definition</b><br>

Who created the Request or the Event. In NHSDigital API's this **SHOULD** always be a PractitionerRole role reference.

This will reference a `contained` PractitionerRole (note: this resource only contains limited user metadata such as ODS Code, professional code and SDS User Profile Id). This resource should not hold data which is held in SDS, only enough information to identify the SDS Entry,

---