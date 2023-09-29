## {{page-title}}

The intended use-case for the `List` profile within GP connect is intended to articulate a two or three level List structure is used to represent structured consultations.

#### List (Consultation)

This top-level profile represents the structured consultation as a whole, and **SHALL** be coded as [325851000000107 | Consultation encounter type (record artifact) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=325851000000107). 

#### List (Topic)

This level represents the Topic / Problem groupings within consultations, and **SHALL** be coded as [25851000000105 | Topic (EHR) (record artifact) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=25851000000105)

#### List (Heading)

This level represents the headings (SOAP heading) levels of the consultation structure that contain record entries, and **SHALL** be coded as [24781000000107 | Category (EHR) (record artifact) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=24781000000107). 

<br />

In the case of consultation which has a "flat" structure, that is, contains record entries without a surrounding Topic / Heading structure, producer systems generate a List(Topic) level which links directly to record entries without the List(Heading) level.

Empty consultations and empty subsections (topics and headings) are suppressed at source and this is reflected in the cardinalities specified.

---