## {{page-title}}

Any information which can be retrieved through use of an existing national service is not expected to be duplicated in messages within the Genomic Medicine Service. Instead, these resources should be referenced, following the {{pagelink:Bundle-referencing}} guidance. 

These services include but are not limited to:
- ODS for organisation search
- SDS for practitioner details
- NRL for resource location
- PDS for patient demographics (A patient resource will still be expected to support consistent querying across patients both registered and not registered with PDS)
- NHS App for patient empowerment

How providers/consumers should integrate with central services is pending a finalised architecture for the Genomic Medicine Service.

## Temporary Registration/ Merge Patients 

The core identifier for a patient is the NHS number. If a patient does not have an NHS number a local ID  is allocated  to identify the patient.  In the event there is a duplication of records of the same patient, the activity of merging/de-merging of records should occur in the source (EPR) systems and inform PDS. Any communication to the core infrastructure should utilise an NHS number. In the event, an NHS number is not available, temporary identifiers (local IDs) may be used. All organisations involved in utilising the genomics service SHALL be PDS compliant. 

The core infrastructure SHALL have the capability to manage merge scenarios in a transparent and auditable manner for the end users. Any superseded tests allocated to a record will be merged into the parent patient record as informed by PDS. 

Where there is no PDS integration, automatic merging of patients within the core infrastructure will not be possible. There may be a potential for duplicate records which will need to be managed through the core source system used within the organisation.  

The expectation is that patients who do not have an NHS number will  have a test request created based on a local identifier (Hospital ID or local ID provided by the originating organisation) to progress the genomics test request and bypass the need to temporarily register the patient.  

In the event there is a duplication of records (same patient), the activity of merging/ de-merging of records should also occur in the local EPR and/or LIMS. Local policies should be followed in the event of merging/de-merging a parent and duplicate record. The subsequent master record (post merge) should display the merged record in downstream systems. 

## Sensitive/Restricted Patient Records

At times, PDS may mark patient records as sensitive, redacting information from responses which may be used to locate a patient. As demographic information is not expected to be duplicated within the central service, for patients registered with PDS, this should not impact the data stored on the central service. In this case, the demographics as well as the sensitive flag for the patient, should be retrieved directly from PDS. 

Where patients are not registered with PDS, it is expected source systems will redact the necessary information (e.g. address, telecom, related persons, GP practice, pharmacy etc.) from the messages sent to the central broker in order to be GDPR/PDS compliant.

While every effort will be made to honour the sensitive nature of patient records, where binary data is uploaded to the central server, as in the case of unstructured reports, this information cannot be redacted by the central service. It is the responsibility of source systems to redact the necessary information from binary files before sending this data to the central broker.

## Data Enrichment and Maintenance

The service will have a road map item to explore and integrate with services such as PDS, NEMS and ODS APIs to check data quality. 

For creation and update of service requests this should not be necessary as there is an expectation that systems connecting to the test order service will have recently verified these details against the same national services, but there will be scenarios such as superseded NHS numbers and deceased patients which will not be captured if a supplier does not interact with the service when this happens, therefore the service would need to be notified or poll PDS to check for updated NHS numbers or changes to deceased status.

## RelatedPerson and familial relationships/linkage

The PDS service currently supports the RelatedPerson resource. Use of this resource is currently limited to representation of carers, next of kin, or other individuals serving as contact points for the patient, with expectations this will extend to proxy relationships in the future. 

While Genomics also uses RelatedPerson, the use case is quite different. Within Genomics, there is the need to represent Biological relationships between individuals to support creation of genetic pedigrees, interpretation/evaluation of inheritance of disease and identifying related family members eligible for cascade testing. 

These biological relationships are currently solely represented within genomic services (e.g. GOMS, UGR) as PDS is limited to relationships in a legal/administrative context. There are a number of concerns regarding representation of biological relationships within a demographics service, e.g. natural father not being the same as the father figure raising a child, which could lead to information governance/legal issues. As such, biological relationships will remain within the purview of genomic services for the forseeable future. 

## Proposed Architecture

{{render:diagrams-architecture}}

Architectural decisions as well as the low level design for the service can be found on the [Genomic Order Management NHS Futures pages](https://future.nhs.uk/NHSgenomics/view?objectId=178297445)