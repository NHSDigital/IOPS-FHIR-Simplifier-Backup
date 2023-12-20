# {{page-title}}

The profile is provided for implementation guidance:
- it is not necessary to reference the profile in the Resource.meta. 

## Usage
The Observation resource is used to hold test results. There are up to 4 Observation resources in a multi-cancer early detection report.
- a grouper observation that organises the observation results
- an observation of whether cancer markers were detected or not
- an observation of the possible primary site for the detected cancer markers
- an observation of the possible secondary site for the detected cancer markers

For a test report that is not marked as cancelled 
- the grouper observation SHALL be present
- the observation for cancer markers detected or not SHALL be present
- the observation of primary site MAY be present (if cancer markers are detected)
- the observation of secondary site MAY be present (if cancer markers are detected and a secondary site is reported)

For a test that is cancelled
- no observations shall be present (and the DiagnosticReport will have a status of 'cancelled')

## Conformance Rules

Reference - {{pagelink:Home/Design/Data-mapping.page.md}}

<iframe src="https://simplifier.net/guide/uk-core-implementation-guide-stu3-sequence/home/profilesandextensions/profile-ukcore-observation?version=1.7.0" height="800px" width="100%"></iframe>



<hr class="thickline">