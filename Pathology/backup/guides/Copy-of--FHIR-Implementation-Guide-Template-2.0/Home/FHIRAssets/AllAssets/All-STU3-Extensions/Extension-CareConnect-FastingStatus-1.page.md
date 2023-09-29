---
topic: STU3ExtensionFastingStatus
---
### Extension-CareConnect-FastingStatus-1
#### Overview
This extension may be used to indicate abstinence or reduction from some or all food, drink, or both, for a period of time prior to specimen collection. **Note:** the definition of this extension is based on the [fastingStatus](https://hl7.org/FHIR/specimen-definitions.html#Specimen.collection.fastingStatus_x_) element that was added to the Specimen resource in FHIR R4.   


* STU3 CareConnect Extension: [Extension-CareConnect-FastingStatus-1](https://simplifier.net/hl7fhircareconnectbaselineforstu3/extension-careconnect-fastingstatus-1)

#### Context of Use
This extension may be used on the following element(s):
* Specimen.collection

#### Example

```xml
    <collection>
        <!--  **************extension start**************  -->
        <extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-FastingStatus-1">
            <valueCodeableConcept>
                <coding>
                    <system value="http://terminology.hl7.org/CodeSystem/v2-0916"/>
                    <code value="F"/>
                    <display value="Patient was fasting prior to the procedure."/>
                </coding>
            </valueCodeableConcept>
        </extension>
        <!--  **************extension end**************  -->
        <collector>
            <reference value="urn:uuid:dc634735-b577-4b6d-8f8e-4be72068506b"/>
        </collector> 
        <collectedDateTime value="2022-04-01T09:00:00+00:00"/>
    </collection>    
```