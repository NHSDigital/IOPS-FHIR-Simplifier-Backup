---
topic: Guidance-NamingSystems
---
## {{page-title}}

This section details the NamingSystems for CodeSystems and Identifiers used within UK Core. It does not include the actual CodeSystems. 

A FHIR NamingSystem is a URL that acts as a well known "name" for the type of another concept, such as an NHS Number (an identifier) or a SNOMED CT code (terminology). 

The name is a machine readable unique string for the scheme of an identifier or code system. When a concept is used in FHIR, such as an identifier in a Patient resource, there needs to be a way to show that it is from the set of NHS Numbers and not some other type of identifier. This concept type is a URL, that acts as a name, and it is used in `identifier.system` or `coding.system`. FHIR Naming System URLs are equivalent to OIDs used in earlier versions of HL7. OIDs can still be used but are deprecated for use in FHIR.

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> Note</h4>
This page is a list of the UK NamingSystem URLs. Each name entry is held in a FHIR NamingSystem resource, within the <a href="https://simplifier.net/guide/UKNamingSystems/Home?version=current">UK FHIR Community Assets IG</a>. It is only the URL itself that is used in actual FHIR data. Software systems only need to use the correct URL, and don’t need to directly deal with the NamingSystem resources.
</div>

More information on NamingSystems is available in the [FHIR standard](https://www.hl7.org/fhir/namingsystem.html).

----