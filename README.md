# Simplifier Project Source Control

This repo contains a back up of IOPS Simplifier projects. Each project has a workflow to unpack, commit, create a PR and merge the current state of the Simplifier project. The original project files can be found [here](https://github.com/NHSDigital/simplifier-project-source-control). 
*Note: Due to Windows PathName limitations changes to this reopitory should be done using a non windows machine, or via the GitHub website.* 

## Prequsites

A valid Simplifier account with write access for private projects.
A Simplifer Project to back up. The name of the project will be referred to as [Project Name], e.g. [HL7 FHIR UK Core R4](https://simplifier.net/hl7fhirukcorer4). Do not include any symbols.

## To add a new project:

- Copy the Project name from the Simplifier url. e.g. http://simplifier.net/<projectname>, e.g. hl7fhirukcore.
- Under `Settings -> Secrets and variables -> Actions` Create a new variable and add the following:
  - Name: <PROJECTNAME> from the url above, but capitalised and special characters removed (-,&, etc.) e.g. HL7FHIRUKCORER4:
  - Value: <projectname>
- Copy the Github Action .github/workflows/z_Template-Backup.yml, and amend the name to <projectname> e.g. hl7fhirukcore.yml
- Within the file find and replace all `REPLACE_WITH_VARIABLE` with the variable name created above, e.g. HL7FHIRUKCORER4
     
If Projects outside HL7 and NHS England Organization, the following will also need amending.
    - line 31: 
        - secrets.[PROJECTNAME]_SIMPLIFIER_PWD
        - secrets.[PROJECTNAME]_SIMPLIFIER_ADDRESS

### Secrets to add:
If Projects outside HL7 and NHS England Organization, the following will need to be added under `Settings -> Secrets and variables -> Actions`.
* [PROJECTNAME]_SIMPLIFIER_USER  
  * Simplifier username that has access to project.  
* [PROJECTNAME]_SIMPLIFIER_PWD  
  * Password for Simplifier user.

Docs on [creating variables for a respository](https://docs.github.com/en/actions/learn-github-actions/variables#creating-configuration-variables-for-a-repository).
Docs on [creating secrets for a respository](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-a-repository).

## Schedule to run

The action is set to run hourly by default in the [action file](.github/workflows/backup.yml#L6).  

To help with calculating the time correctly see [Cronitor - a cron job calculator](https://crontab.guru/)
Further info on using a [scheduled cron job](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#schedule) in an action.


### API request:
* See Firely docs on project zip using the [Simplifier API](https://docs.fire.ly/projects/Simplifier/features/api.html#project-zip-api)
 
## Configuration of GITHUB_TOKEN

GITHUB_TOKEN has been setup with the default permissions granted to run workflows in this repository, for more details see [GitHub docs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-github-actions-settings-for-a-repository#setting-the-permissions-of-the-github_token-for-your-repository).

## Configuration of branches to delete automatically

This repository has been set up to automatically delete merged branches, for more details see [GitHub docs](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/managing-the-automatic-deletion-of-branches)
