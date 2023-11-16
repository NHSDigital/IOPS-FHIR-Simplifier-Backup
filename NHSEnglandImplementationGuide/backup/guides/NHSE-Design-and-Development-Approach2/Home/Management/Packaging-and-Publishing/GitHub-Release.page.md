 ## {{page-title}}

 ### Prerequisites

1. From the current burger bar select Export.

{{render:GithubRelease}}

### Creating a Release Within GitHub
1. With the GiHub NHSEngland-FHIR-ImplementationGuide repository. Select the Releases title on the right-hand side.
2. Select Draft a new release.
3. Ensure target is set to main and create a tag the is the same as the package version.
4. Add the following release notes, changing the information as needed:

    ### For the balloted release

    Implementation Guide<br>
    INSERT URL


    Package<br>
    INSERT URL

    NPM<br>
    Note: The npm package contains only active FHIR assets, and does not        include retired assets, or ones in development which are not part of        this formal release, and therefore these are not referenced in the STUx     Sequence Implementation Guide.

    npm --registry https://packages.simplifier.net install package@version


    ### For the non-balloted release
    Implementation Guide<br>
    INSERT URL

    Package<br>
    INSERT URL

    NPM<br>
    Note: The npm package contains all current FHIR assets, including ones       in development which are not part of this formal release, and               therefore these are not referenced in the x.x.x Implementation Guide.

    npm --registry https://packages.simplifier.net install package@version

5. Drag and drop the exported IG file into the ‘Attach binary…’ area.
6. Set as latest release and publish.