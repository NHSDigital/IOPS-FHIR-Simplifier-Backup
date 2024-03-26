## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

A default value of `unknown` **SHOULD** be used for open or complete referrals as generally the status of referrals is not consistently maintained in a GP patient record. A status of `cancelled` **MAY** be used where the GP System has directly cancelled a referral, for example cancelled via eRS. Referrals `entered in error` **MUST NOT** be included.

<i class="fa fa-link"></i> [Code System Request Status](http://hl7.org/fhir/R4/codesystem-request-status.html)

<h5><ins>Example</ins></h5>

```xml
<status value="unknown" />
```

---