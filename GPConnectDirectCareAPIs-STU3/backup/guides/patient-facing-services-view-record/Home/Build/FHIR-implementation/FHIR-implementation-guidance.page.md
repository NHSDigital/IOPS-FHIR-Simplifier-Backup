## {{page-title}}

The purpose of the implementation guide is to describe adaptations of the base FHIR specification specific for GP Connect First of Type (FoT) implementations. It therefore focuses mainly on any additional constraints and specialisations from the base specification that apply to GP Connect. The complete specification therefore comprises the base FHIR specification plus the constraints and specialisations described herein. Where there is a conflict between the base specification and this web page, this web page shall take precedence.

### FHIR overview

As outlined on the official [HL7® FHIR](http://hl7.org/fhir/STU3/) website:

> FHIR (Fast Health Interoperability Resources) is designed to enable information exchange to support the provision of healthcare in a wide variety of settings. The specification builds on and adapts modern, widely used RESTful practices to enable the provision of integrated healthcare across a wide range of teams and organisations.

#### [FHIR versions](http://hl7.org/fhir/STU3/versions.html)

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
     <i class="fas fa-exclamation-circle text-primary"></i> <b>Note</b>: This page is written to accompany the currently released version of FHIR which is Standard For Trial Use (STU) 3.
</div>

STU3 is a pre-release version of FHIR standard and as such is expected to evolve and develop over time. NHS Digital expects FHIR clients and servers (developed as part of GP Connect) to be maintained and uplifted to newer versions of the FHIR® standard as they become available and are staged into the GP Connect programme.

When a new release of the FHIR standard has been published for use NHS Digital will carry out an impact assessment of all FHIR resources used by the GP Connect API project to determine the impact of transitioning to the new FHIR release. Following this assessment, the FHIR resource library will be updated to include resources using this new release. NHS Digital will work with consumers and providers throughout this transition phase and are expected to maintain both versions of the FHIR release until it has been agreed that the old version can be deprecated.

### FHIR implementations

The Health Level Seven (HL7®) International standards body maintains a list of open source FHIR implementations on its [Wiki](http://wiki.hl7.org/index.php?title=Open_Source_FHIR_implementations). Currently five FHIR server implementations and a number of client libraries are available as open source software. These are written in a variety of popular programming languages, such as Java, C#.NET, JavaScript and Python.

<div class="alert alert-success nhsd-t-body" role="alert">
	<i class="fa fa-check text-success"></i> <b>Tip:</b> NHS Digital strongly recommends that software vendors use (and contribute back to) an existing open source FHIR library to both help accelerate development and to grow/mature the open source FHIR ecosystem.
</div>

### FHIR in scope

To help API implementers deal with the FHIR learning curve, NHS Digital has worked to constrain the scope of the FHIR® standard that is expected to be implemented in the first tranche of development work as follows:

1. [Resource](https://www.hl7.org/fhir/STU3/resource.html)
    1. [Resource identity](https://www.hl7.org/fhir/STU3/resource.html#id)
    2. [Business identifiers](https://www.hl7.org/fhir/STU3/resource.html#identifiers)
2. [Domain resource](https://www.hl7.org/fhir/STU3/domainresource.html)
    1. Common API
        1. [Patient](https://www.hl7.org/fhir/STU3/patient.html) profiled as gpconnect-patient-1.
        2. [Practitioner](https://www.hl7.org/fhir/STU3/practitioner.html) profiled as gpconnect-practitioner-1.
        3. [Organisation](https://www.hl7.org/fhir/STU3/organization.html) profiled as gpconnect-organization-1.
        4. [Location](https://www.hl7.org/fhir/STU3/location.html) profiled as gpconnect-location-1
    2. Care record API
        1. Please refer to the [Resource data types](https://gp-connect-1-6-2.netlify.app/development_fhir_api_guidance#ResourceDataType) section of this page.
    3. Bookings API
        1. [Schedule](https://www.hl7.org/fhir/STU3/schedule.html) profiled as gpconnect-schedule-1
        2. [Slot](https://www.hl7.org/fhir/STU3/slot.html) profiled as gpconnect-slot-1
        3. [Appointment](https://www.hl7.org/fhir/STU3/appointment.html) profiled as gpconnect-appointment-1
3. [Resource metadata](https://www.hl7.org/fhir/STU3/resource.html#Meta)
    1. [Profile](https://www.hl7.org/fhir/STU3/resource.html#metadata)
    2. [Version Id](https://www.hl7.org/fhir/STU3/resource.html#metadata)
4. [Bundle](https://www.hl7.org/fhir/STU3/bundle.html)
5. [Data types](https://www.hl7.org/fhir/STU3/datatypes.html)
    1. [Primitive types](https://www.hl7.org/fhir/STU3/datatypes.html#primitive)
        1. All primitive types SHALL be supported.
    2. [Complex types](https://www.hl7.org/fhir/STU3/datatypes.html#complex)
        1. The following complex types SHALL be supported.
            1. [Identifier](https://www.hl7.org/fhir/STU3/datatypes.html#identifier)
            2. [Coding](https://www.hl7.org/fhir/STU3/datatypes.html#codeableconcept)
            3. [Codeable Concept](https://www.hl7.org/fhir/STU3/datatypes.html#coding)
            4. [Period](https://www.hl7.org/fhir/STU3/datatypes.html#period)
        2. It is expected that further complex types will be introduced as required to model structured data.
6. Interactions
    1. Instance
        1. [READ](https://www.hl7.org/fhir/STU3/http.html#read)
        2. [UPDATE](https://www.hl7.org/fhir/STU3/http.html#update)
        3. [DELETE](https://www.hl7.org/fhir/STU3/http.html#delete)
    2. Type level
        1. [CREATE](https://www.hl7.org/fhir/STU3/http.html#create)
        2. [SEARCH](https://www.hl7.org/fhir/STU3/http.html#search)
7. [Search](https://www.hl7.org/fhir/STU3/http.html#search)
    1. [Search parameter types](https://www.hl7.org/fhir/STU3/search.html#ptypes)
        1. [Date](https://www.hl7.org/fhir/STU3/search.html#date)
        2. [Token](https://www.hl7.org/fhir/STU3/search.html#token)
        3. [Reference](https://www.hl7.org/fhir/STU3/search.html#reference)
    2. [Search prefixes](https://www.hl7.org/fhir/STU3/search.html#prefix)
        1. lt (less than)
        2. le (less or equal to)
        3. gt (great than)
        4. ge (greater or equal to)
        5. eq (equal to)
    3. Parameters for all resources
        1. [_query](https://www.hl7.org/fhir/STU3/search.html#query)
        2. [_list](https://www.hl7.org/fhir/STU3/search.html#list)
    4. Search result parameters
        1. [_include](https://www.hl7.org/fhir/STU3/search.html#include) can be used internally inside a named `_query` operation.
        2. [_sort](https://www.hl7.org/fhir/STU3/search.html#sort) can be used internally inside a named `_query` operation.
8. [Operations](https://www.hl7.org/fhir/STU3/operations.html)
    1. [Implementation defined operations](https://www.hl7.org/fhir/STU3/operations.html#extensibility)

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <i class="fas fa-exclamation-triangle text-danger"></i> <b>Important</b>: It is fully expected that over time new areas of the FHIR® standard will be brought into scope as new capabilities are requested and vendors’ understanding of FHIR® standard matures. This is in line with the agreed iterative/Agile engagement process that has been agreed between the NHS Digital and the principal GP system vendors.
</div>

### FHIR out of scope

GP Connect provider systems are not expected to implement the following aspects of the FHIR® standard under the scope of the first tranche of development work:

1. Operations
    1. Validate a resource
    2. Meta operations
    3. Generate a document
    4. Process message
    5. Find a functional list
    6. ConceptMap operations
    7. Closure table maintenance
    8. Fetch records
    9. Questionnaire operations
    10. Terminology operations
2. Interactions
    1. Instance
        1. HISTORY
        2. [VREAD](https://www.hl7.org/fhir/STU3/http.html#vread)
    2. Type level
        1. HISTORY
    3. Whole system
        1. BATCH TRANSACTION
        2. HISTORY
        3. SEARCH
    4. Conditional interactions
        1. CREATE
        2. UPDATE
        3. DELETE
3. Search
    1. Parameter types
        1. Number
        2. String
        3. Quantity
        4. Composite
        5. URL
    2. Parameters for all resources
        1. _language
        2. _lastUpdate
        3. _tag
        4. _profile
        5. _security
        6. _text
        7. _content
        8. _filter
    3. Search result parameters
        1. _count
        2. _summary
        3. _elements
        4. _contained
        5. _containedType
    4. Chained parameters
    5. Paging / Page count
4. Resource metadata
    1. lastUpdated
    2. security
    3. tag


<div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body">
    <i class="fas fa-exclamation-circle"></i> <b>Warning</b>: Providers are free to implement additional FHIR functionality above that mandated under the GP Connect delivery if they so desire. However, the Spine Secure Proxy (SSP) will only forward accredited system interactions.
</div>

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <i class="fas fa-exclamation-circle text-primary"></i> <b>Note</b>: It is fully expected that over time new areas of the FHIR® standard will be brought into scope as new capabilities are requested and vendors’ understanding of FHIR® standard matures. This is in line with the agreed iterative/Agile engagement process that has been agreed between the NHS Digital and the principal GP system vendors.
</div>

### FHIR system conformance

Provider systems SHALL provide read-only [FHIR CapabilityStatement resources](https://www.hl7.org/fhir/STU3/capabilitystatement.html) that identify all the profiles and operations that each FHIR server supports for each resource type.

A FHIR server’s capability statement SHALL be available using the following [capabilities interactions](http://hl7.org/fhir/STU3/http.html#capabilities):

```
GET [base]/metadata {?_format=[mime-type]}
```

Please note: The `[base]` portion may vary based on the GP Connect capability.

Refer to:

- [Get the FHIR capability statement (Foundations)]() for the capability statement describing the Foundations and Appointment Management capabilities
- [Get the FHIR capability statement (Access Record Structured)]() for the capability statement describing the Access Record Structured capability
### FHIR resource conformance

To help a consumer find the correct set of reports for a use-case, a provider of resources SHALL, for any profile declared in [CapabilityStatement.profile](https://www.hl7.org/fhir/STU3/profiling.html#2.13.0.3.2), mark resources with profile assertions documenting the profile(s) they conform to. A provider of resources SHOULD also ensure that any resource instance that would reasonably be expected to conform to the declared profiles SHOULD be published in this form.

### GP Connect FHIR API conformance

GP Connect comprises a number of RESTful API bundles. Each API bundle is intended to support sets of related use cases, for example the Appointment API bundle supports viewing, booking and cancelling GP appointments in a number of scenarios.

Individual API bundles may be provided independently of each other. GP Connect conformance may be claimed in relation to one or more API bundles. A provider claiming to provide an API bundle must be fully conformant (that is, implement all the resource profiles and interactions for the API bundle as specified in this document and all the general requirements described herein).

### Incomplete data - expected behaviour

Where resource instance data available in clinical systems is either insufficient or corrupt and thus a resource cannot be constructed by a provider system which meets the associated FHIR profile, the following guidance describes expected behaviour:

**Scenario: GET resource by logical ID**

An HTTP 500 error should be returned with an OperationOutcome resource providing diagnostic details. This may include details of the resource in the location element.

**Scenario: FHIR response bundles**

When a response bundle contains multiple resources, one or more of which cannot be populated as available data does not enable the resource in question to be populated to validate the associated profile, the provider will behave as follows: The request as a whole will error with a 500 HTTP Status returned, together with the appropriate OperationOutcome resource providing diagnostic detail of the error.

---