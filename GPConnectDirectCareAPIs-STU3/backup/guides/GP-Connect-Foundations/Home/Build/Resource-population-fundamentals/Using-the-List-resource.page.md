## {{page-title}}

The `List` resource in FHIR is used to manage collections of resources.

In GP Connect, it is used to organise data returned by a query into groups of resources that can then be processed more easily. For each clinical area query, GP Connect will return a list that identifies the data returned for that query.

- when an API call returns data for more than one clinical area, the list will identify which data has been returned for which clinical area
- where there are no items returned, the list will be empty
- where the return includes warning messages (for example, when clinical data is excluded), those messages will be in the list profile.manage negation where no resources are present in a system to be returned by a query - an attribution that is common to the resources it references will be returned, differentiating between items at different stages of a workflow, providing a mechanism to deal with warnings that can be applied to the group of resources
