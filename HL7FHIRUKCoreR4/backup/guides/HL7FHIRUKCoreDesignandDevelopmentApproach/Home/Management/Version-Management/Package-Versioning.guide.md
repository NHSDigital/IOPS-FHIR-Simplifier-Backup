## {{page-title}}

The UK Core uses Simplifier NPM packages to release the FHIR Conformance Assets. From STU2 every package SHALL contain the snapshot and differential elements within each Profile. The profiles within GitHub SHALL only contain the differntial element, with the snapshot being rendered when the package is created using the Simplifer Bake scripting.

The UK Core Packages are located with the <a href="https://simplifier.net/HL7FHIRUKCoreR4/~packages">Project Packages area.</a>

Further information on Packages is available in the  <a href="https://docs.fire.ly/projects/Simplifier/data_governance_and_quality_control/simplifierPackages.html">Simplifier documentation</a> and <a href="https://confluence.hl7.org/display/FHIR/NPM+Package+Specification"> HL7 Confluence</a>.

These packages may be used to validate conformance of an implementation of FHIR against a particular version or versions of the UK Core. For more information on conformance to UK Core see the {{pagelink:Claiming-Conformance-to-UK-Core}} .

The Simplifier NPM pages are released as part of a UK Core release and normally coincides with an an Implementation Guide release. The NPM package name format is all lower case and as described below:

<code>fhir.<i>[fhir version]</i>.ukcore.<i>[sequence release] [major].[minor].[patch]</i></code>

where

- <code><i>[fhir version]</i></code> - The release version of FHIR used with the UK Core (currently R4).
- <code><i>[sequence release]</i></code> - The sequence and release (currently stu1).
- <code><i>[major]</i></code> - The major release aligns with the Implementation Guide major version and is indicative of the number of ballots the Implementation Guide has been through.
- <code><i>[minor]</i></code> - The minor version aligns with the Implementation Guide minor version.
- <code><i>[patch]</i></code> - The patches release is used for bug fixes within the package. The patch version starts at 0 and increments by 1 for every package release for a particular Implementation Release. Note: a Implementation guide may have more than one package associated with it. 

### Package example

For example `fhir.r4.ukcore.stu1 0.1.0`


---

<!--Original
The Simplifier NPM packages are released as part of a UK Core release, normally contaning an Implementation Guide and a NPM Package. The NPM package is named based on a seven-item string (1_2_3_4_5_6_7) which is described below:

`fhir`_"fhir version"_`ukcore`_"sequence_release"_"major version"_"minor version"_patch version"`

<ol>
<li>A fixed value <code>fhir</code></li>
<li>The release version of FHIR used with the UK Core (currently R4)</li>
<li>A fixed value <code>ukcore</code></li>
<li>The sequence and release (currently stu1)
<li>The major release aligns with the Implementation Guide major version and always 0 unless the release has been though a ballot</li>
<li>The minor version aligns with the Implementation Guide minor version</li>
<li>The patch version starts at 0 and increments by 1 for every package release for a particular Implementation Release. Note: a Implementation guide may have more than one package associated with it.
</ol>

### Package example

For example `fhir.r4.ukcore.stu1 0.1.0`
 -->
