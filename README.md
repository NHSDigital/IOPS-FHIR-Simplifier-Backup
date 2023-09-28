# Simplifier Project Source Control

This repo contains a back up of IOPS Simplifier projects. Each project has a workflow to unpack, commit, create a PR and merge the current state of the Simplifier project.  

## Prequsites

A valid Simplifier account.

## To add a new project:

- Create a new folder named after the Simplifier Project ensuring all whitespaces are removed, e.g. HL7FHIRUKCoreR4. This will be referred to as [ProjectFolderName]. 
- Within the folder create a new README.md with a link to the project
- Copy the Github Action .github/workflows/Backup.yml, and prefixing the project name to the filename, e.g. HL7FHIRUKCoreR4-Backup.yml
- Within the yml file change the following to refer to the [ProjectFolderName] created above:
    - line 1:
        - [ProjectFolderName] Back Up
    - line 31:
        - secrets.[PROJECTFOLDERNAME]_SIMPLIFIER_USER 
        - secrets.[PROJECTFOLDERNAME]_SIMPLIFIER_PWD
        - secrets.[PROJECTFOLDERNAME]_SIMPLIFIER_ADDRESS

## Schedule to run

The action is set to run hourly by default in the [action file](.github/workflows/backup.yml#L6).  

Further info on using a [scheduled cron job](https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows#schedule) in an action.

## Respository secrets and variables required

Under `Settings -> Secrets and variables -> Actions` add the following, where [PROJECTFOLDERNAME] is the name given to the folder above, capitalised, e.g. HL7FHIRUKCORER4:

### Secrets to add:
* [PROJECTFOLDERNAME]_SIMPLIFIER_USER  
  * Simplifier username that has access to project.  
* [PROJECTFOLDERNAME]_SIMPLIFIER_PWD  
  * Password for Simplifier user.

### Variables to add:

* [PROJECTFOLDERNAME]_SIMPLIFIER_ADDRESS
  * Address of project - e.g. `https://api.simplifier.net/<project>/zip`
  * See Firely docs on project zip using the [Simplifier API](https://docs.fire.ly/projects/Simplifier/features/api.html#project-zip-api)

Docs on [creating variables for a respository](https://docs.github.com/en/actions/learn-github-actions/variables#creating-configuration-variables-for-a-repository).
Docs on [creating secrets for a respository](https://docs.github.com/en/actions/security-guides/encrypted-secrets#creating-encrypted-secrets-for-a-repository).

## Configuration of GITHUB_TOKEN

GITHUB_TOKEN has been setup with the default permissions granted to run workflows in this repository, for more details see [GitHub docs](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-github-actions-settings-for-a-repository#setting-the-permissions-of-the-github_token-for-your-repository).

## Configuration of branches to delete automatically

This repository has been set up to automatically delete merged branches, for more details see [GitHub docs](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/managing-the-automatic-deletion-of-branches) 

