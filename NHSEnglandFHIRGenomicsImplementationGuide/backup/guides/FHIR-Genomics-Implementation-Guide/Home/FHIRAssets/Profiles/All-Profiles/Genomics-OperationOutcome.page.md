## {{page-title}}

The Genomics OperationOutcome is the same as provided within FHIR R4. The FHIR R4 OperationOutcome is provided below for completeness.

OperationOutcomes are expected for any create or update operations made on the server resulting in validation messages (or any create or update operations made within a transaction bundle). It is not expected that connecting systems would need to construct OperationOutcome resources or submit these to the server, though key elements within the resource are detailed here for receiving systems.

It is expected that all issue codes raised by the Genomic Medicine Service will fall under existing codes bound in the below resource. If further codes are needed, these will be promoted to UK Core for release in a future ballot/sprint.

| Profile url | FHIR Module | Normative Status |
|--
| [http://hl7.org/fhir/StructureDefinition/OperationOutcome](https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/OperationOutcome&scope=hl7.fhir.r4.core@4.0.1) | [HL7 International]() | trial-use |

<br>

<br>

<div class="nhsd-!t-margin-bottom-6">
    <ul class="nav nav-tabs" role="tablist">
        <li role="presentation" class="active">
            <a href="#Profile" role="tab" data-toggle="tab">Profile</a>
        </li>
        <li role="presentation">
            <a href="#Differential" role="tab" data-toggle="tab">Differential</a>
        </li>
        <li role="presentation">
            <a href="#Constraints" role="tab" data-toggle="tab">Constraints</a>
        </li>
        <li role="presentation">
            <a href="#Examples" role="tab" data-toggle="tab">Examples</a>
        </li>
        <li role="presentation">
            <a href="#Mappings" role="tab" data-toggle="tab">Mappings</a>
        </li>
    </ul>
    <div class="tab-content snippet">
        <div id="Profile" role="tabpanel" class="tab-pane active">
            <br />
            {{tree:http://hl7.org/fhir/StructureDefinition/OperationOutcome, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/OperationOutcome}} <br>
            <br />
            {{tree:http://hl7.org/fhir/StructureDefinition/OperationOutcome, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:http://hl7.org/fhir/StructureDefinition/OperationOutcome, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:OperationOutcome-SuccessfulValidation-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url=':http://hl7.org/fhir/StructureDefinition/OperationOutcome'
            for differential.element.constraint
            select key, human, severity, expression
            ```
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
            <br />
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td></td><td></td><td></td></tr>
                </table>
        </div>
    </div>
</div>

### Additional Guidance

- <a href="#issue">issue</a>

<a name="issue"></a>
#### issue
An issue element will be included within the OperationOutcome for each issue that needs to be communicated to the requesting system, e.g. errors, warnings or informational messages. Appropriate 'severity' and 'code' codes will be assigned to help categorization of an messages returned, using the standard HL7 bound ValueSets. 

The `diagnostics` field will be used to present a human readable version of the message and `location` will be used to detail the location within the request payload that resulted in the associated issue/message.

If an error or warning is returned, the 'details' element will be populated with any validation specific messages. Details of the systems and codes used for these messages will be determined by the validation package used by the central order management broker (this is still to be determined at the time of publication).
```json
"issue":[
            {
              "severity":"error",
              "code":"processing",
              "details":{
                "coding":[
                  {
                    "system": "http://terminology.hl7.org/CodeSystem/operation-outcome",
                    "code": "MSG_LOCAL_FAIL",
                    "display": "Unable to resolve local reference to resource Patient/Patient-MeirLieberman-Example"
                  }
                ]
              },
              "diagnostics": "Validation errors occurred during processing",
              "location": [
                  "Bundle.entry[1].resource.ofType(ServiceRequest)"
              ]
            }
          ]
```