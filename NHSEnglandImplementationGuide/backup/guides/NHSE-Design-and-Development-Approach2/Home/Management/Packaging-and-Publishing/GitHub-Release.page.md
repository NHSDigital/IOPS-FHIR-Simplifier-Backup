## {{page-title}}

### Prerequisites

1. From the current burger bar select Export.

    {{render:GithubRelease}}

### Creating a Release Within GitHub
1. With the GiHub NHSEngland-FHIR-ImplementationGuide repository. Select the Releases title on the right-hand side.

    {{render:Github}}

2. Select Draft a new release.
3. Ensure target is set to main and create a tag that is  same as the package version.
4. Add the following release notes, changing the information as needed:

    ## Simplifier FHIR Assets
    ### Implementation Guide
    - INSERT URL <br>
    example:  [1.0.0 - STU1]                                  (https://simplifier.net/guide/nhs-england-implementation-guide-stu1?version=1.0.0)
 

    ### Package
    - INSERT URL <br>
  example: [fhir.r4.nhsengland.stu1 1.0.0]          (https://simplifier.net/packages/fhir.r4.nhsengland.stu1/1.0.0)


    ### NPM
      Note: The npm package contains only active FHIR assets, and does not        include retired assets, or ones in development which are not part of        this formal release, and therefore these are not referenced in the          STUx Sequence Implementation Guide. <br>
  npm --registry https://packages.simplifier.net install package@version<br>
  example: `npm --registry https://packages.simplifier.net install        fhir.r4.nhsengland.stu1@1.0.0`

5. Drag and drop the exported IG file into the ‘Attach binary…’ area.
6. Set as latest release and publish.