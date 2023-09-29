## {{page-title}}

<h5><ins>Guidance</ins></h5>

The `meta.security` contains details on whether the patient consents for updating their record and sharing on patient facing services. `NOPAT` label can be used from the following code system `http://hl7.org/fhir/v3/ActCode`

The following guidance should be used when populating the security tag:

-	**Patient consents for updating patient record and sharing on patient facing services** - Full details of an Encounter are sent without security label 
 - **Patient consents for updating patient record but does not consent to share on Patient Facing Services** - 	Full details of an Encounter are sent with `NOPAT` security label



<h5><ins>Example</ins></h5>

```xml
<meta>
    <security>
        <coding>
            <system value="http://hl7.org/fhir/v3/ActCode" />
            <code value="NOPAT" />
            <display value="no disclosure to patient, family or caregivers without attending provider's authorization" />
        </coding>
    </security>
</meta>

```

---