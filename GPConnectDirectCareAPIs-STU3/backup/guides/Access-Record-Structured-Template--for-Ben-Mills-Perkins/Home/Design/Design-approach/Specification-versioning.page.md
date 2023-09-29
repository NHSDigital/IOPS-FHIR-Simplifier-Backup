## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Summary</b>: An overview of how the specification (and other technical assets) are versioned
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Important</b>: This page describes the standard by which the specification and other artefacts are versioned. To see a list of specification versions and the capabilities available at those versions, please see the <a href="https://digital.nhs.uk/services/gp-connect/develop-gp-connect-services/specifications-for-developers">specification versions page.
</div>

### Introduction

<b>GP Connect API specification releases are assigned a single version number from 23 February 2018 onwards.</b>

The automated test suite, demonstrator and other artefacts released in line with the specification are also assigned the same single version number.

This supersedes the previous scheme whereby the constituent capability packs were released and versioned independently.

</br>

### Version number standard

The specification version number is based on the Semantic [Versioning 2.0.0](https://semver.org/) standard.

<br />

{{render: versionNumberStandard.png}}

<br />

When a specification is released, the version number is incremented as follows:

- <b>Major</b> version when breaking changes are made

- <b>Minor</b> version when larger non-breaking changes or unsubstantive breaking changes are made, for example a new capability; or a significant number of smaller non-breaking changes or unsubstantive breaking changes are made

- <b>Patch</b> version when smaller non-breaking changes or unsubstantive breaking changes are made

</br>

### Types of change

#### Breaking changes
Breaking changes are those changes made to the specification that require a provider to update their GP Connect API implementation and would cause a consuming system built to any minor or patch version of the same major version of the specification to break.

Breaking changes are therefore issued in a new major version of the specification, in order to allow consuming systems built to previous versions to continue to operate at the previous major version without breaking.

#### Unsubstantive breaking changes
An breaking change may be classified as an unsubstantive breaking change where:

- providers and consumers have not built against any minor or patch version of the same major version of the specification, and therefore the change is not breaking in practice

- or in consultation with providers and/or consumers, where providers and/or consumers are in the process of building against any minor or patch version of the same major version of the specification

Where this occurs, previous minor or patch versions of the specifications will either be discontinued (see below), or will be amended to include warnings regarding the changed functionality, to ensure consuming (and providing systems) do not build against the changed functionality in the future.

#### Non-breaking changes
Non-breaking changes are:

- changes made to the specification that do not require a provider to update their API implementation

- changes made to the specification that do require a provider to update their API implementation but do not cause a consuming system built to any minor or patch version of the same specification to break

- or other types of guidance or supporting material not classified above

#### Stylistic changes and clarifications
The version number may not be incremented when stylistic changes are made for example, section renumbering, broken links, style corrections, typos, and improvements to the clarity of wording that do not change the meaning of the specification.

#### Pre-release (draft) labels
When a <B>pre-release label</B> is appended to the version number with a hyphen it indicates the maturity of the GP Connect API defined in that specification.

<table data-responsive>
    <thead>
        <tr>
            <th>Pre-release label</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>alpha</td>
            <td>API that is still active development and subject to change</td>
        </tr>
        <tr>
            <td>beta</td>
            <td>API that is largely complete and unlikely to change substantially, but still need further testing by a wider group of implementers before becoming live</td>
        </tr>
        <tr>
            <td>(no label)</td>
            <td>Live release API</td>
        </tr>
        <tr>
            <td>discontinued</td>
            <td>API which have been discontinued and should not be used for new development</td>
        </tr>
    </tbody>
</table>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
<b>Important</b>: The pre-release labels definitions above apply to GP Connect API specification versions 0.7.2 and newer, and GP Connect API specification versions 1.2.4 and newer. For older specifications, please refer to the pre-release label definitions on the specification versioning page in those specifications.
</div>

</br>

### Associated technical artefacts
The following GP Connect API artefacts are released as part of or alongside the specification, taking the same version number as the specification:

- {{pagelink:Home/Design/Explore/GP-Connect-Demonstrator.page.md}}

- {{pagelink:Home/Design/Explore/Interactive-API-documentation.page.md}}

- Provider automated test suite ({{pagelink:Home/Build/Test-and-assure/Testing-assets.page.md}})

- SDS interaction IDs (see below)

- Service Root URL format (see below)

The following GP Connect API artefacts are released alongside the specification, but use their own version number scheme:

- FHIR Profiles ({{pagelink:Home/Build/FHIR-development/FHIR--resources.page.md}})

#### SDS interaction IDs
SDS {{pagelink:Home/Authentication/Integrate-with-Spine/Interaction-IDs.page.md}} change only when a new major version of the specification is released and are suffixed with the major version number, except for GP Connect API versions 0.x.x where there is no suffix.

#### Service Root URL format
'Service Root URL versioning' - ({{pagelink:Home/Build/General-API-guidance.page.md}}) contain the major version number of the specification.