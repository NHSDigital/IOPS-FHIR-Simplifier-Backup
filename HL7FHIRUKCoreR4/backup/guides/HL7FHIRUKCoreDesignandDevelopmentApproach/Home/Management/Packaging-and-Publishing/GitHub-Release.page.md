## GitHub Release

### Prerequisites

<ol>
<li>From the current burger bar select Export.
 <br><br>
 {{render:igoverwitepublish}}
 <br><br>
</li>
</ol> 

### Creating a Release Within GitHub

<ol>
<li>With the GiHub FHIR-R4-UKCORE-STAGING-MAIN repository. Select the Releases title on the right-hand side.
 <br><br>
{{render:IGGithubRelease}}
  <br><br></li>
<li>Select Draft a new release.</li>
<li>Ensure target is set to main and create a tag the is the same as the package version.</li>
<li>Add the following release notes, changing the information as needed:

#### For the balloted release
```
Implementation Guide
INSERT URL

Package
INSERT URL

NPM
Note: The npm package contains only active FHIR assets, and does not include retired assets, or ones in development which are not part of this formal release, and therefore these are not referenced in the STUx Sequence Implementation Guide..

npm --registry https://packages.simplifier.net install package@version
```

#### For the non-balloted release
```
Implementation Guide
INSERT URL

Package
INSERT URL

NPM
Note: The npm package contains all current FHIR assets, including ones in development which are not part of this formal release, and therefore these are not referenced in the x.x.x Implementation Guide.

npm --registry https://packages.simplifier.net install package@version
```

</li>
<li>Drag and drop the exported IG file into the ‘Attach binary…’ area.</li>
<li>Set as latest release and publish.</li>
</ol>

<hr class="thickline">