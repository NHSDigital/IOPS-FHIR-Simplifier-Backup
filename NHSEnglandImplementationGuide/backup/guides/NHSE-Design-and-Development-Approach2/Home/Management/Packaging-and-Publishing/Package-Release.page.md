## {{page-title}}

Prerequisites
Ensure the following has been checks have been completed:

- All relevant Jira tickets are complete
- Ensure all GitHub PR's are complete
- Merge develop (hotfix) into relevant main (release)

Publishing a Package

Note that the following must be done within a virtual machine due to NHS firewall restrictions.

1. Within the Simplifier Project reimport Github.


Image

2. Within the same menu, check the GitHub repository settings.

The Repository include/exclude textbox should be as the following:

by default, everything is included 
if some include statements are added, we will exclude everything by default 
Simplifier imports only xml, json, images, css, yaml and markdown file types 

Include examples: 
 FHIR/IG/** 
 *.xml 

Exclude examples: 
 !FHIR/*.img 
 !*.cs 
 !FHIR/examples/* 

 Exclude all capability statement files: 
!CapabilityStatement/*