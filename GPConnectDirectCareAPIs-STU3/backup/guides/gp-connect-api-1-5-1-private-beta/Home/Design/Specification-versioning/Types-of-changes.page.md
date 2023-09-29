## {{page-title}}

### Breaking changes
Breaking changes are those changes made to the specification that require a provider to update their GP Connect API implementation and would cause a consuming system built to any minor or patch version of the same major version of the specification to break.

Breaking changes are therefore issued in a new major version of the specification, in order to allow consuming systems built to previous versions to continue to operate at the previous major version without breaking.

### Unsubstantive breaking changes
An breaking change may be classified as an unsubstantive breaking change where:

- providers and consumers have not built against any minor or patch version of the same major version of the specification, and therefore the change is not breaking in practice

- or in consultation with providers and/or consumers, where providers and/or consumers are in the process of building against any minor or patch version of the same major version of the specification

Where this occurs, previous minor or patch versions of the specifications will either be discontinued (see below), or will be amended to include warnings regarding the changed functionality, to ensure consuming (and providing systems) do not build against the changed functionality in the future.

### Non-breaking changes
Non-breaking changes are:

- changes made to the specification that do not require a provider to update their API implementation
- changes made to the specification that do require a provider to update their API implementation but do not cause a consuming system built to any minor or patch version of the same specification to break
- or other types of guidance or supporting material not classified above

### Stylistic changes and clarifications
The version number may not be incremented when stylistic changes are made for example, section renumbering, broken links, style corrections, typos, and improvements to the clarity of wording that do not change the meaning of the specification.

## Pre-release (draft) labels
When a pre-release label is appended to the version number with a hyphen it indicates the maturity of the GP Connect API defined in that specification.

| Pre-release label   |     Description      | 
|----------|-------------:|
| alpha |  API that is still active development and subject to change | 
| beta |   API that is largely complete and unlikely to change substantially, but still need further testing by a wider group of implementers before becoming live   |  
| (no label) | Live release API |  
| discontinued | API which have been discontinued and should not be used for new development | 



