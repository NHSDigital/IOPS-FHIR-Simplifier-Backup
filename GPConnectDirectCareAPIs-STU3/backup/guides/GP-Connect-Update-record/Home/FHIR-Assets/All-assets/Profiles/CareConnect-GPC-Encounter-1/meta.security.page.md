## {{page-title}}

<h5><ins>Guidance</ins></h5>

The `meta.security` contains details on whether the patient consents for updating their record and sharing on patient facing services. `NOPAT` label can be used from the following code system `http://hl7.org/fhir/v3/ActCode`

-	Full details of an Encounter are sent without security label - Patient consents for Updating Patient Record and sharing on Patient Facing Services
-	Full details of an Encounter are sent with security label - Patient consents for Updating Patient Record but does not consent to share on Patient Facing Services
- Full details of an Encounter are not sent and sent with security label - Patient does not consent to Update Record and therefore also does not consent to share on Patient Facing Services (log encounter but don’t add full details to patient record). For this instance only the mandatory fields in the encounter profile should be sent, all non-mandatory resources should be omitted from the payload.



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