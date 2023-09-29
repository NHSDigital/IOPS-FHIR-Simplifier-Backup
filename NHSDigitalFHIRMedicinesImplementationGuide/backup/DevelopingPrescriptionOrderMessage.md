### Developing Prescription Order Message

#### Overview

The FHIR Message Bundle that is sent to EPS MUST following the rules in this MessageDefinition {{pagelink:prescription-order.md}}

This Bundle consists of several resources and is designed to allow reuse of resources from other services. 

* Patient from PDS
* Practitioner from SDS (not currently a FHIR enabled service)
* PractitonerRole from SDS (not currently a FHIR enabled service)
* Organization from SDS or ODS (STU3)
* Signature from EPS Signing Services 

MedicationRequest has to be constructed but this resource should be forward compatible with other UK Core based system, i.e. it can be reused. 

The use of these services to source these resources is not necessary and any UK Core can be used. However the resources MUST also follow the rules within this ImplementationGuide. In other words the EPS will not accept FHIR resources that don't meet the data requirements of EPS. 
<br>

| Important |
|--
| EPS will not not reject messages that exceed EPS requirements, it will not process them and these will NOT be pass onto downstream systems (e.g. pharmacists). |


<br><br>
#### Use of Meta 

The *tolerant* principle outlined above is a change in the use of the meta elements in FHIR resources. Previous UK Implementation Guides mandated/suggested profile conformance within the meta section, e.g. 
 
 ```json
{
  "resourceType": "MedicationRequest",
  "meta": {
    "profile": [
      "https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-MedicationRequest-1"
    ]
  }
}
```


This example states the resource conforms to the https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-MedicationRequest-1 profile. In EPS this is not necessary, the EPS API's will check all resources against EPS profiles. If you wish to include a meta section it SHOULD state the relevant UK-Core profile, e.g. 

 ```json
{
  "resourceType": "MedicationRequest",
  "meta": {
    "profile": [
      "https://fhir.nhs.uk/StructureDefinition/UKCore-MedicationRequest"
    ]
  }
}
```
<br>

| Resource Validation |
|--
| Unlike STU3 where profile complinace was stated in resources, R4 focuses on the receiving service checking compliance according to the rules it needs to follow |












