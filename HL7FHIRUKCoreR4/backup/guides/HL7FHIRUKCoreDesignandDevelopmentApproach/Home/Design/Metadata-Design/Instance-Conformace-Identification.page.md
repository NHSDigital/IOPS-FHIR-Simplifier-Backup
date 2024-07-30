## {{page-title}}

For some information flows, there is a requirement to identify which UK Core profile(s) an instance being exchanged between healthcare IT systems conforms to. This could be for the purpose of validation of the instance against the profile definition and/or for conformance testing. This profile conformance is declared using the profile.meta element. The element carries the profile URL appended with the version information. 

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Most implementations will use NPM Packages for validation and therefore the use of this approach is not mandated when using UK Core profiles. More information about NPM packages is available on the {{pagelink:Package-Versioning}} page.  </div>

The format is: 'URL' "\|" 'version'
For example:

<code>https://fhir.nhs.uk/R4/StructureDefinition/UKCore-RelatedPerson|1.1.0</code>

This is illustrated below:

````xml
<RelatedPerson xmlns="http://hl7.org/fhir">
    <id value="RP123" />
    <meta>
        <profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-RelatedPerson|1.1.0" />
    </meta>
````

see [HL7 - Record Versions vs Business Versions vs FHIR Versions](https://www.hl7.org/fhir/R4/resource.html#versions)

---