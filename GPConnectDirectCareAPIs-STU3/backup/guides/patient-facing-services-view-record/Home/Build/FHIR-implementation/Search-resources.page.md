## {{page-title}}

A simple [search](https://www.hl7.org/fhir/STU3/http.html#search) is executed by performing a `GET` request optionally accompanied by zero or more name-value URL encoded parameters:

```
GET [base]/[resourcetype]?name=value&...
```

In order to enable searching by date/time range, servers SHALL support the following prefixes as defined in the base FHIR specification for date parameters: eq, gt, lt, ge, le.

To search for all the appointments for a patient that occurred over a 2-year period:

```
GET [base]/Patient/1A6E1B1C-6340-4663-926C-9CD1306EAAF8/Appointment?start=ge2014-01-01&start=le2015-12-31
```

### Chained parameters

Servers SHALL support searching by a [chained](https://www.hl7.org/fhir/STU3/search.html#2.1.1.4.13) `Patient` identifier parameter for references to `Patient` resources that conform to the `GP-Patient` profile (and therefore have an NHS number identifier). For example:

```
GET [base]/AllergyIntolerance?patient.identifier=http://fhir.nhs.net/Id/nhs-number|1234569876
```

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <i class="fas fa-exclamation-triangle text-danger"></i> <b>Important</b>: GP Connect clients and servers are not expected to support arbitrary ad hoc searching.
</div>

### Search example: Search for a patient resource by business ID

#### Request

```
GET [base]/Patient?identifier=http://fhir.nhs.net/Id/nhs-number|9900002831
```

If a patient resource for NHS number 9900002831 exists then the server SHALL return a bundle containing all patient resources with the specified NHS number identifier.

#### Response

```
<Bundle>
 <Patient xmlns="http://hl7.org/fhir">
  <id value="1A6E1B1C-6340-4663-926C-9CD1306EAAF8" />
  <meta>
   <profile value="http://fhir.nhs.net/StructureDefinition/gpconnect-patient-1" />
  </meta>
  <identifier>
   <system value="http://fhir.nhs.net/Id/nhs-number" />
   <value value="9900002831" />
  </identifier>
  <name>
   <use value="usual" />
   <family value="Smith" />
   <given value="Mike" />
   <prefix value="Mr" />
  </name>
  <birthDate value="1977-01-09" />
  <address>
   <use value="home" />
   <type value="both" />
   <line value="2, The Green" />
   <city value="Harrogate" />
   <district value="Yorkshire" />
   <postalCode value="HG1 4AF" />
  </address>
 </Patient>
</Bundle>
```

### Advanced search

Servers SHALL implement the [_query](https://www.hl7.org/fhir/STU3/search.html#query) search parameter to enable custom-named search profiles to be defined and used which describe a specific query operation.

```
GET [base]/[resourcetype]?_query=[query_name]&name=value&...
```

Servers SHOULD implement the standard search equivalent of the advanced custom-named search for queries defined under the GP Connect FoT.

#### Request

```
GET [base]/Schedule?_query=getschedule&date=ge2016-05-12&date=le2016-05-26
```

#### Response

```
<Bundle xmlns="http://hl7.org/fhir">
  <type value="searchset"/>
</Bundle>
```