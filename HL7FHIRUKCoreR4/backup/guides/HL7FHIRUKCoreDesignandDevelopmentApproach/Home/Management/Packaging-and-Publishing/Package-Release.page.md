## Package Release

### Prerequisites
Ensure the following checks have been completed:
-	All relevant Jira tickets are complete
-	Ensure all GitHub PR's are complete
-	Merge develop (hotfix/release) into relevant main (release) branch

### Bake Command
Ensure the package.bake.yml is configured to add snapshots to Profiles. See Simplifier's <a href="https://docs.fire.ly/projects/Simplifier/data_governance_and_quality_control/simplifierPackages.html#bake-pipeline">Bake PipeLine</a> and <a href="https://simplifier.net/docs/bake">Bake Syntax for more details</a>.

### Publishing a Package

<ol>
<li>Within the Simplifier Project reimport Github.
<br><br>
{{render:igimport}}
<br><br></li>
<li>Within the same menu, check the GitHub repository settings. 
<br><br>
The Repository include/exclude textbox should be as the following:

```
#by default, everything is included 
#if some include statements are added, we will exclude everything by default 
#Simplifier imports only xml, json, images, css, yaml and markdown file types 

#Include examples: 
# FHIR/IG/** 
# *.xml 

#Exclude examples: 
# !FHIR/*.img 
# !*.cs 
# !FHIR/examples/* 

# Exclude all capability statement files: 
!CapabilityStatement/*
```
 
This ensures that the capability statement is not copied into the npm package.
If the textbox had to be updated open the file manager, search for “capability” and if there delete.
<br><br>
{{render:igfilemanager}}
<br><br>
{{render:igcapabilitystatement}}
</ol>

--- 

### Creation of the NPM Package

<ol>
<li>Create the new package for the relevant version
<br><br>
{{render:ignewpackage}}
<br><br></li>
<li>Enter the version number. This should be in the format of x.x.x(-aaa) where x denotes a number and (-aaa) denote an optional lowercase string. For example, 1.0.0-pre-release.
<br><br>
{{render:ignewpackageversion}}
<br><br>
For the release package the release notes should read

#### For the balloted release
```
This is a release of the FHIR assets for the x.x.x version of the UK Core.

**Please note: This npm package contains only the current active FHIR assets, and does not include retired assets, or ones in development which are not part of this formal release, and are therefore these are not in the associated Implementation Guide.**
```

#### For the non-balloted release
```
This is a release of the FHIR assets for the x.x.x version of the UK Core

**Please note: This npm package contains all current assets, including ones in devlopment which are not part of this formal release, and therefore theres are not in the associated Implementation Guide.**
```
</li>
<li>Within the content tab ensure the appropriate checkboxes are selected as below:
<br><br>
{{render:ignewpackageboxes}} 
<br><br></li>
<li>Click Publish.
 <br><br>
The package has been created.</li>
</ol>

<hr class="thickline">