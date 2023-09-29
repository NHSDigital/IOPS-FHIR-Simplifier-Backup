## Guide versioning

This page gives details of the versioning approach for this guide.

It will be a generic approach and this page will either have default text created, which
may require small tweaks, or provide a link to a generic page elsewhere.

## Release Candidate ##

This implementation guidance is the **Release Candidate** release to support the development of the Digital Child Health Event Messages. 

## Semantic Versioning ##

Given a version number MAJOR.MINOR.PATCH, increment the:

- MAJOR version when you make incompatible API changes,
- MINOR version when you add functionality in a backwards-compatible manner, and
- PATCH version when you make backwards-compatible bug fixes.

Additional labels for pre-release and build metadata are available as extensions to the MAJOR.MINOR.PATCH format.

A pre-release version MAY be denoted by appending a hyphen (refer to [Semantic Versioning - Item 9](http://semver.org/#spec-item-9){:target="_blank"})

For example: 1.0.0-alpha.1 is a valid pre-release version.

## Pre-release Labels ##

These labels will be taken from the GDS development process stages, and will be one of:

 - **Experimental**: Early development/POC version of an API for early sight during discovery
 - **Alpha**: Initial test APIs, likely to change substantially, or be discontinued as the project develops
 - **Beta**: APIs that are still under active development and subject to change, but that are likely to progress into a live API
 - **Release Candidate**: APIs that are largely complete, unlikely to change substantially, but still need further testing before becoming live
 - **Live**: Release live APIs
 - **Discontinued**: APIs which have been discontinued and should not be used for new development.