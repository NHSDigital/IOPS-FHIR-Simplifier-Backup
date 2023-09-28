# Simplifier Project Source Control

This repo contains a back up of IOPS Simplifier projects. Each project has a workflow to unpack, commit, create a PR and merge the current state of the Simplifier project.  

## Prequsites

A valid Simplifier account.
A Simplifer Project to back up. The name of the project will be referred to as [Project Name], e.g. [HL7 FHIR UK Core R4](https://simplifier.net/hl7fhirukcorer4). Do not include any symbols.

## To add a new project:

- Create a new folder named after the Simplifier Project ensuring all whitespaces are removed, e.g. HL7FHIRUKCoreR4. This will be referred to as [ProjectFolderName].
- Within the folder create a new README.md with a link to the project
- Copy the Github Action .github/workflows/Backup.yml, and prefixing the project name to the filename, e.g. HL7FHIRUKCoreR4-Backup.yml
- Within the yml file change the following:
    - line 1:
        - [Project Name] Back Up
    - line 27:
        - [ProjectFolderName]
    - line 31:
        - secrets.[PROJECTNAME]_SIMPLIFIER_USER 
        - secrets.[PROJECTNAME]_SIMPLIFIER_PWD
        - secrets.[PROJECTNAME]_SIMPLIFIER_ADDRESS

## Schedule to run

The action is set to run hourly by default in the [action file](.github/workflows/backup.yml#L6).  

To help with calculating the time correctly see [Cronitor - a cron job calculator](https://crontab.guru/)
Further info on using a [scheduled cron job](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#schedule) in an action.

## Respository secrets and variables required

Under `Settings -> Secrets and variables -> Actions` add the following, where [PROJECTNAME] is the name given to the folder above, capitalised, e.g. HL7FHIRUKCORER4:

### Secrets to add:
* [PROJECTNAME]_SIMPLIFIER_USER  
  * Simplifier username that has access to project.  
* [PROJECTNAME]_SIMPLIFIER_PWD  
  * Password for Simplifier user.

### Variables to add:

* [PROJECTNAME]_SIMPLIFIER_ADDRESS
  * Address of project - e.g. `https://api.simplifier.net/<project>/zip`
  * See Firely docs on project zip using the [Simplifier API](https://docs.fire.ly/projects/Simplifier/features/api.html#project-zip-api)

Docs on [creating variables for a respository](https://docs.github.com/en/actions/learn-github-actions/variables#creating-configuration-variables-for-a-repository).
Docs on [creating secrets for a respository](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-a-repository).

## Configuration of GITHUB_TOKEN

GITHUB_TOKEN has been setup with the default permissions granted to run workflows in this repository, for more details see [GitHub docs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-github-actions-settings-for-a-repository#setting-the-permissions-of-the-github_token-for-your-repository).

## Configuration of branches to delete automatically

This repository has been set up to automatically delete merged branches, for more details see [GitHub docs](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/managing-the-automatic-deletion-of-branches) 

