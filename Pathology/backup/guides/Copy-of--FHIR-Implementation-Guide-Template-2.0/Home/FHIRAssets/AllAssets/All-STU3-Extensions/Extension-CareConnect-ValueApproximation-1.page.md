---
topic: STU3ExtensionValueApproximation
---
### Extension-CareConnect-ValueApproximation-1
#### Overview
This extension may be used to indicate that a numeric test result (defined using [Observation.valueQuantity](http://hl7.org/fhir/STU3/observation-definitions.html#Observation.value_x_)) represents an approximate value. This is a boolean extension. It is recommended that this extension is NOT used when reporting exact values i.e. when valueBoolean would be false.

* STU3 CareConnect Extension: [Extension-CareConnect-ValueApproximation-1](https://simplifier.net/hl7fhircareconnectbaselineforstu3/extension-careconnect-valueapproximation-1)

#### Context of Use
This extension may be used on the following element(s):
* Observation.valueQuantity

#### Example

```xml
    <valueQuantity>
        <!--  **************extension start**************  -->
        <extension url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-ValueApproximation-1">
            <valueBoolean value="true" />
        </extension>
        <!--  **************extension end**************  -->
        <value value="10"/>
        <unit value="g/L"/>        
    </valueQuantity>
```