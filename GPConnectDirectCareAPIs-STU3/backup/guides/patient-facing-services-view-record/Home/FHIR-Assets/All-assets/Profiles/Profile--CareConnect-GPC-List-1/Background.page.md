## {{page-title}}

The `List` profile is used to manage collections of resources.

In GP Connect, it is used to organise data returned by a query into groups of resources that can then be processed more easily. For each clinical area query, GP Connect will return a list that identifies the data returned for that query.

- when an API call returns data for more than one clinical area, the list will identify which data has been returned for which clinical area
- where there are no items returned, the list will be empty
- where the return includes warning messages (for example, when clinical data is excluded), those messages will be in the list profile.manage negation where no resources are present in a system to be returned by a query - an attribution that is common to the resources it references will be returned, differentiating between items at different stages of a workflow, providing a mechanism to deal with warnings that can be applied to the group of resources

### Using the List resource for consultation queries

The results of a query for consultation details **MUST** return a `List` containing references to all the `Encounter` resources which represent each consultation that is returned.

The `List` **MUST** be populated in line with the guidance on `List` resources.

If the `List` is empty, then an empty `List` **MUST** be returned with an `emptyReason.code` with the value `no-content-recorded`. In this case, `List.note` **MUST** be populated with the text ‘Information not available’.

#### List (Consultation)

This top-level profile represents the structured consultation as a whole, and **SHALL** be coded as [325851000000107 | Consultation encounter type (record artifact) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=325851000000107). 

#### List (Topic)

This level represents the Topic / Problem groupings within consultations, and **SHALL** be coded as [25851000000105 | Topic (EHR) (record artifact) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=25851000000105)

#### List (Heading)

This level represents the headings (SOAP heading) levels of the consultation structure that contain record entries, and **SHALL** be coded as [24781000000107 | Category (EHR) (record artifact) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=24781000000107). 

<br />

In the case of consultation which has a 'flat' structure, that is, it contains record entries without a surrounding Topic / Heading structure, producer systems generate a List(Topic) level which links directly to record entries without the List(Heading) level.

Empty consultations and empty subsections (topics and headings) are suppressed at source and this is reflected in the cardinalities specified.

---