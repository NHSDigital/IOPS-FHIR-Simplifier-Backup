## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> Work in progress. This page is for illustration of a concept</div>

In EPS it is not currently possible to retrieve a prescription once it has been downloaded using {{pagelink:PrescriptionRelease}}. 
This API interaction will allow this and is an extension to the {{pagelink:PrescriptionAPI.md}}
It does this by supporting the [_include and _revinclude](https://www.hl7.org/fhir/search.html#revinclude) parameters.

The returned FHIR Bundle will be of type `searchset`, not a `message`, the resources entries will be the same.

### MedicationRequest

| FHIR Exchange | API | FHIR Resource Profile | 
|--
| FHIR RESTful  | GET /MedicationRequest?group-identifier=(prescription-order-reference)&_include=(includes)&_revinclude:iterate=MessageHeader.focus | {{pagelink:NHSDigital-MedicationRequest.md}} | 

includes - Only support for wild card (* - asterix) will be initially supported.  

#### Example

To return a prescription with a short form prescription order number of 83C40E-A23856-00123C.

`GET /MedicationRequest?group-identifier=83C40E-A23856-00123C&_include=*&_revinclude:iterate=MessageHeader.focus`

To return a continuous-repeat-dispensing order (a orginal-order, not a reflex order). 

`GET /MedicationRequest?group-identifier=83C40E-A23856-00123C&_include=*&_revinclude:iterate=MessageHeader.focus`
