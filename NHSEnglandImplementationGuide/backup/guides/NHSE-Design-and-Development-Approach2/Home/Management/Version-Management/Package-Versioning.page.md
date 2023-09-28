## {{page-title}}

The NHS England IG uses Simplifier NPM packages to release the FHIR Conformance Assets.

The NHSE Packages are located with the <a href="https://simplifier.net/NHS-England-Implementation-Guide/~packages">Project Packages area.</a>

<a href="https://docs.simplifier.net/projects/Firely-Terminal/Managing-Packages.html?highlight=simplifier%20packages">Further information on Packages is available in the Simplifier documentation.</a>

These packages may be used to validate conformance of an implementation of FHIR against a particular version or versions of the NHS England IG. 

The Simplifier NPM pages are released as part of a NHS England release and normally coincides with an Implementation Guide release. The NPM package name format is all lower case and as described below:

fhir.[fhir version]nhsengland.[sequence release] [major].[minor].[patch]

where

- <code>[fhir version]</code> - The release version of FHIR used with the NHS England (for example, R4).
- <code>[sequence release]</code> - The sequence and release (for example, stu1).
- <code>[major]</code> - The major release aligns with the Implementation Guide major version.
- <code>[minor]</code> - The minor version aligns with the Implementation Guide minor version.
- <code>[patch]</code> - The patch version starts at 0 and increments by 1 for every package release for a particular Implementation Release. Note: a Implementation guide may have more than one package associated with it.

### Package example

For example 'fhir.r4.nhsengland.stu1 1.0.0`


---
