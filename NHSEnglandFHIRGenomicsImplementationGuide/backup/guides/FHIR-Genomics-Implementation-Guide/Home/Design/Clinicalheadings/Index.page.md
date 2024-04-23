## {{page-title}}

Clinical headings are created by bodies such as the PRSB and are used to add structure to the FHIR instance. 

Across the GLHs, there is a lack of standardisation within paper based Non-WGS Test Order Forms used for both Cancer and Rare Disease. To enable interoperability and ensure the provision of end-to-end visibility on the test order, a standardised master data set (MDS) has been compiled, which serves all scenarios and test types. The MDS has been mapped to each test type in the genomic test directory, effectively creating a by-test mapping and therefore the minimum data set requirements for each permutation of the future test order forms. 

The standardisation of the Non-WGS Test Order form is currently underway. Fields within the test order forms (Non-WGS and WGS) are specified as Mandatory, Optional, or Mandatory-if (applicable to test type) based on the MDS. The functional requirements for test ordering include an ability to configure forms based on the MDS and an ability to update forms (including introduction and modification of data fields through change control processes) at a regional level. For further details, refer to the draft copies of the Non-WGS Test Order forms in the links to documentation section. 

In the case of Genomics, no PRSB clinical headings have been used but sections from the core Genomics Minimum Dataset and their mappings have been recreated on the following pages. The current dataset is based on **MDS v1.03, available on the [NHS Futures website](https://future.nhs.uk/NHSgenomics/view?objectId=194236741)**. These include designations of mandatory vs. optional fields per test category, which have been excluded from the following tables for readability. 

The sub pages provide guidance about the heading and the structure required when representing this information in FHIR.

**For preliminary reports included in a test order, e.g. Pathology etc. These should be included as "presentedForm" attachments in DiagnosticReports with a small clinical conclusion included in the "conclusion" field. If supported, sending systems can also send coded Observations following the Genomics-Observation profile.**

## Specialist Testing Requirements 

The Master Data Set (MDS) sets out the data required by both the requester and lab, to accept and progress the test request. In addition to the mandatory and optional fields identified on the Non-WGS and WGS test order forms, there may be additional specialist testing requirements needed to progress the test. 

For example, to request an NIPD test the following additional information is required:

- Identification of Foetal Phenotypic sex (Mandatory)- Male/Female/ Undetermined/ Unknown (free text field)
- Foetal Count (Mandatory) -identification of number of fetuses
- Foetal ID: practices for recording the ID may vary across local organisations
- Pregnancy details including capture of pregnancy type (spontaneous pregnancy, IVF or surrogacy and age of egg donor)
- Ultrasound or MRI Reports (Optional)

The requirement for electronic test order forms is to allow for configuration and inclusion of additional specialist testing needs. The by test mapping is currently in progress and requires input from the GMS to progress with inclusion of the additional requirements into the alpha phase.

## Mapping to HL7v2/IHE

The current genomics space largely uses HL7 v2. There are multiple versions of HL7 v2 being used and many local variations on the standards.

The long term plan is to move to FHIR R4 UK Core, but as this is a risk to delivering the alpha for the test order service the following options for transforming the HL7 v2 messages to FHIR for the test order service are being considered:

1. Transform HL7 v2 messages within the test order service
2. Suppliers perform their own mapping of HL7 v2 to FHIR and interact with the test order service using the FHIR APIs
3. Centrally define a mapping from one or two of the most common HL7 v2 versions to FHIR, so that it can be given to suppliers to implement.
4. Transformation Component/Service, deployed locally

The following are currently inside the scope of this work (matched to IHE Pathology and Laboratory Medicine, PaLM, profiles):

- Test requesting procedure - IHE Laboratory Testing Workflow (LTW)
- DiagnosticReport distribution - IHE Sharing Laboratory Reports (XD-LAB)
- Send-away test communications - IHE Inter-Laboratory Workflow (ILW)
- Requests for further clinical information - IHE Laboratory Clinical Communications (LCC)
- Sample event tracking - IHE Specimen Event Tracking (SET)

The following are currently outside the scope of this work

- Laboratory device integration - IHE Laboratory Device Automation (LDA)
- Internal laboratory procedures - IHE Laboratory Analytical Workflow (LAW)
- Point of care testing - IHE Laboratory Point of Care Testing (LPOCT)
- Sample identification - IHE Laboratory Specimen Barcode Labelling (LBL)
- Local lab code sharing - IHE Laboratory Code Set Distribution (LCSB)
- Structured reporting - IHE Anatomic Pathology Structured Report (APSR)

**The original order message in FHIR has been mapped to the HL7v2.5.1 OML Laboratory Order Message (event O21). as defined withing the IHE PaLM Laboratory Testing Workflow Technical Framework. The mappings provided in the following tables are meant as a guide to support uplifting current HL7v2 interfaces within the Genomic Order Comms ecosystem, not as a recommendation on the representation of FHIR concepts within HL7v2.**

Further pages may be added to include additional mappings to FHIR, such as:

- Mapping another data standard to FHIR
- Mapping from another version of a HL7 standard
- Mapping data items defined in a clinical domain to FHIR

The mapping may be at a resource level or Bundle level.

These pages provide mapping of the business entities and data to FHIR resources. The constraints that need to be applied to each FHIR resource using the UK Core profiles is provided on the individual profile pages elsewhere within this Implementation Guide.