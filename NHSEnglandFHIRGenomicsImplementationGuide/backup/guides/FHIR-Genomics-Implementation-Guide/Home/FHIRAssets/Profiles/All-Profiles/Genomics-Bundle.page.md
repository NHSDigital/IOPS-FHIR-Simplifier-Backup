## {{page-title}}

The Genomics Bundle is currently pending Clinical and Technical Assurance of the base UKCore resource. Once this profile becomes active in UKCore its suitability for use and need for profiling within Genomics will be assessed. 

The profile for the UKCore-Bundle is provided below for completeness.

Bundles within Genomics will be limited to Transactions for Test orders and updates; Transaction-responses for responses to transactions (housing sets of OperationOutcomes); or Searchsets, returned in response to search queries.

| Profile url | FHIR Module | Normative Status |
|--|
| [http://hl7.org/fhir/StructureDefinition/Bundle](https://simplifier.net/resolve?target=simplifier&canonical=http://hl7.org/fhir/StructureDefinition/Bundle&scope=hl7.fhir.r4.core@4.0.1) | [HL7 International]() | trial-use |

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
            {{tree: http://hl7.org/fhir/StructureDefinition/Bundle, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link:http://hl7.org/fhir/StructureDefinition/Bundle}} <br>
            <br />
            {{tree:http://hl7.org/fhir/StructureDefinition/Bundle, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict:http://hl7.org/fhir/StructureDefinition/Bundle, hybrid}}
        </div>
        <div id="Examples" role="tabpanel" class="tab-pane">
            <br />
            <table>
                <tr>
                    <td>
                    {{pagelink:Bundle-NonWGSTestOrderForm-CancerSolidTumor-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Bundle-NonWGSTestOrderForm-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                    {{pagelink:Bundle-NonWGSTestOrderForm-FetalScenario-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Bundle-NonWGSTestOrderForm-Reanalysis-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Bundle-WGSRoD-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Bundle-WGSTestOrderForm-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Bundle-TransactionResponseError-Example}}
                    </td>
                </tr>
                <tr>
                    <td>
                        {{pagelink:Bundle-TransactionResponseSuccess-Example}}
                    </td>
                </tr>
            </table>
        </div>
        <div id="Constraints" role="tabpanel" class="tab-pane">
            <br />
            @```
            from StructureDefinition
            where url=':http://hl7.org/fhir/StructureDefinition/Bundle'
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

<br>

### Additional Guidance

- <a href="#type">type</a>
- <a href="#total">total</a>
- <a href="#link">link</a>
- <a href="#entry">entry</a>

<a name="type"></a>
#### type
The type of Bundle. This is expected to be `transaction` for Bundles POSTed to the central broker, `transaction-response` for responses to transaction Bundles returned by the broker and `searchset` for collections of resources returned in response to search (GET) requests, as per standard HTTP FHIR rules.
```json
"type": "transaction",
```

<a name="total"></a>
#### total
Only relevant for searchset Bundles. Details the number of resources in the bundle matching the search criteria, not including resources included via the _include criteria.
```json
"total": 3,
```

<a name="link"></a>
#### link
Only relevant for searchset bundles. Details the query string that resulted in the searchset (to allow future queries using the same parameters). `"relation": "self"` will only ever be used.

Links related to response pagination such as next/prev are pending Non-Functional Requirements finalisation for the order management central broker.
```json
"link": [
        {
            "relation": "self",
            "url": "https://api.service.nhs.uk/genomic-order-management-service/FHIR/R4/Specimen/?_include=Specimen%3Asubject&identifier=RGT03135"
        }
    ],
```

<a name="entry"></a>
#### entry

**Transactions**

An entry in the bundle. For transaction Bundles, each entry SHOULD contain a fullURL to ensure resources in the Bundle can reference each other, these can be the locations within the source system or urn:uuids. 

Resources are expected to contain ids to allow referencing within Bundles, though these will be replaced by server assigned ids when saved by the central broker. If additional identifiers need to be persisted e.g. NHS Number, these should be captured within the identifier field. 

Transaction Bundle entries also SHALL contain a request object, specifying the method (either PUT for updates or POST for creates) and the url to send the resource to (equivalent to the resource type for the resource).

Reference to the associated Patient. This MAY be through a resource reference if the ID on the central service is known (or provided within the transaction bundle) or through NHS number where this is known and has been traced through PDS
```json
"entry": [
        {
			"fullUrl": "http://example.org/fhir/Specimen/Specimen-BloodEDTA-Example",
			"resource": {
				"resourceType": "Specimen",
				"id": "Specimen-BloodEDTA-Example",
				"identifier": [
					{
						"system": "https://fhir.add.nhs.uk/Id/specimenId",
						"value": "RGT03135"
					}
				],
				"status": "unavailable",
				"type": {
					"coding": [
						{
							"system": "http://snomed.info/sct",
							"code": "445295009",
							"display": "Blood specimen with EDTA"
						}
					]
				},
				"subject": {
					"reference": "Patient/Patient-MeirLieberman-Example",
					"identifier": {
						"system": "https://fhir.nhs.uk/Id/nhs-number",
						"value": "9449307873"
					}
				},
				"request": [
					{
						"reference": "ServiceRequest/ServiceRequest-NonWGSTestOrderForm-Example"
					}
				]
			},
            "request": {
                "method": "POST",
                "url": "Specimen"
            }
		}
	]
```

**Transaction Responses**

These Bundles are returned in response to transaction requests. These will only contain OperationOutcome resources (one for each recource contained in the transaction request). See {{pagelink:Acknowledgementsandresponses}} for more information. 

These entries will contain a response object detailing the response status of the individual resource operation and an OperationOutcome detailing any relevant diagnostics, such as validation messages. 

Entries will also contain a location element, detailing the relative path of the resource, where the operation has resulted in a resource being created or updated. These URLs will be version specific (using the _history suffix to denote the version number of the resource) if the resource has been updated.
```json
"entry": [
    {
      "response": {
        "status": "201 Created",
        "location": "ServiceRequest/4d70678c-81e4-4ff4-8c67-17596fd0aa46/",
        "lastModified": "2024-01-30T12:01:24Z",
        "outcome": {
          "resourceType": "OperationOutcome",
          "meta": {
            "lastUpdated": "2024-01-30T12:01:24Z"
          },
          "issue": [
            {
              "severity": "information",
              "code": "informational",
              "diagnostics": "No issues detected during validation."
            }
          ]
        }
      }
    }
  ]
```

**Searchsets**

These Bundles are returned in response to GET requests without an ID. entries within these bundles will depend on the endpoint queried and the search parameters included. 

Each entry is expected to include a fullUrl identifying the URL that can be used to retrieve the resource on the server; the resource itself; and a search element detailing whether the resource was included in the search response due to it matching the query parameters, `"mode": "match"`, or whether it was included via the _include parameter, `"mode": "include"`. 
```json
"entry": [
        {
            "fullUrl": "https://api.service.nhs.uk/genomic-order-management-service/FHIR/R4/44707473",
            "resource": {
                "resourceType": "Specimen",
                "id": "44707473",
                "meta": {
                    "versionId": "1",
                    "lastUpdated": "2024-05-13T14:28:05.843+00:00",
                    "source": "#CJ6XJLTGD315XL2Z"
                },
                "identifier": [
                    {
                        "system": "https://fhir.add.nhs.uk/Id/specimenId",
                        "value": "RGT03135"
                    }
                ],
                "status": "unavailable",
                "type": {
                    "coding": [
                        {
                            "system": "http://snomed.info/sct",
                            "code": "445295009",
                            "display": "Blood specimen with EDTA"
                        }
                    ]
                },
                "subject": {
                    "reference": "Patient/44707475",
                    "identifier": {
                        "system": "https://fhir.nhs.uk/Id/nhs-number",
                        "value": "9449307946"
                    }
                },
                "request": [
                    {
                        "reference": "ServiceRequest/ServiceRequest-NonWGSTestOrderForm-Example"
                    }
                ]
            },
            "search": {
                "mode": "match"
            }
        }
    ]
```