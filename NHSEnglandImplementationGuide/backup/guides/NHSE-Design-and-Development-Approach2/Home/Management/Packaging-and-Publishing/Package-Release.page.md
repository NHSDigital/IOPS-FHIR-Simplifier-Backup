## {{page-title}}

### Prerequisites  
Ensure the following checks have been completed:

- All relevant Jira tickets are complete
- Ensure all GitHub PR's are complete
- Merge develop (hotfix/release) into relevant main (release) branch

### Publishing a Package

Note that the following must be done within a virtual machine due to NHS firewall restrictions.

1. Within the Simplifier Project reimport Github.

    {{render:Reimport}}

2. Within the same menu, check the GitHub repository settings.

   The Repository include/exclude textbox should be as the following:
    {{render:Capability}}


   This ensures that the capability statement is not copied into the npm       package. If the textbox had to be updated open the file manager, search     for “capability” and if there delete.

{{render:FileManager}}

### Creation of the NPM Package

1. Create the new package for the relevant version

    {{render:NewPackage}}

2. Enter the version number. This should be in the format of x.x.x(-aaa) where x denotes a number and (-aaa) denote an optional lowercase string. For example, 1.0.0-pre-release.

    {{render:Version}}

    For the release package the release notes should read<br>

    ### For the balloted release<br>
    This is a release of the FHIR assets for the x.x.x version of the NHS       England.

    **Please note: This npm package contains only the current active FHIR       assets, and does not include retired assets, or ones in development         which are not part of this formal release, and are therefore these are      not in the associated Implementation Guide.**

    ### For the non-balloted release<br>

    This is a release of the FHIR assets for the x.x.x version of the NHS       England.

    **Please note: This npm package contains all current assets, including      ones in devlopment which are not part of this formal release, and           therefore theres are not in the associated Implementation Guide.**

3. Within the content tab ensure the appropriate checkboxes are selected as below:
    {{render:Content}}

4. Click Publish.
The package has been created.

---------------------------------------