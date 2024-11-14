---
topic: Profile-UKCore-FamilyMemberHistory
issue: UKCore-FamilyMemberHistory
subject: https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory
expand: yes
---

## StructureDefinition {{variable:issue}}

For collecting relevant Family Member History to aid interpretation of Genomic results. This is limited to collection of Pedigree information. The FamilyMemberHistory resource is not to be used to record participants involved in testing, e.g. in the case of Duo/Trio scenarios (in this case the RelatedPerson resource SHOULD be used instead.

The Genomics FamilyMemberHistory is currently pending Clinical and Technical Assurance of the base UKCore resource. Once this profile becomes active in UKCore its suitability for use and need for profiling within Genomics will be assessed. 
<!--
The draft profile for the UKCore-FamilyMemberHistory is provided below for completeness.

<br>
The CareConnect profile will be uplifted to the R4 UKCore in a future release
<br>
-->

| Profile url | FHIR Module | Normative Status |
|--
| [https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory](https://simplifier.net/resolve?target=simplifier&canonical=https://fhir.hl7.org.uk/StructureDefinition/UKCore-FamilyMemberHistory&scope=fhir.r4.ukcore.stu2@2.0.1-pre-release) | [UKCore]() | trial-use |


{{page:Home-FHIRAssets-Profiles-All-Profiles-UKCoreProfilesTemplatePage}}

<div id="Examples" class="tabcontent">
           <br>
            <ul>
            <li>{{pagelink:FamilyMemberHistory-MildCognitiveDisorder-Example}}
            </ul>
  </div>      

<div id="Mappings" class="tabcontent">
            <br>
                <table class="assets">
                    <tr><th>FHIR</th><th>MDS</th><th>HL7v2</th></tr>
                    <tr><td>FamilyMemberHistory</td><td>Pedigree details/diagram, Disease penetrance</td><td>N/A not in scope for HL7v2, could be added as additional DG1 segments related to relatives (representation of family history in HL7v2 still pending investigation)</td></tr>
                </table>
</div>

<div id="Feedback" class="tabcontent">
{{page:Home-FeedbackTemplate-FeedbackLink}}
</div>

<br>
<h3 id='non-fql-header'> Additional Guidance </h3>

- <a href="#extension:genetics-observation">extension:genetics-observation</a>
- <a href="#identifier">identifier</a>
- <a href="#status">status</a>
- <a href="#patient">patient</a>
- <a href="#relationship">relationship</a>


<a name="extension:genetics-observation"></a>
<h4 class='additional-Guidance-Submenu'> extension:genetics-observation </h4>
An extension on the FamilyMemberHistory resource to include Observations relevant to Genomic testing/interpretation. 

```json
"extension":  [
        {
            "url": "http://hl7.org/fhir/StructureDefinition/family-member-history-genetics-observation",
            "valueReference": {
                "reference": "Observation/Observation-BloodPressure-Example"
            }
        }
    ],
```

<a name="identifier"></a>
<h4 class='additional-Guidance-Submenu'> identifier </h4>
This SHOULD be NHS number or local identifier (if NHS number is unavailable e.g. for non UK residents). If a local identifier is used, an assigner SHALL be provided.
The FamilyMemberHistory.identifier field SHALL match the identifier used for a RelatedPerson resource if the same person is being referenced.

```json
   "identifier": {
      "system": "urn:oid:2.16.840.1.113883.2.1.3.2.4.18.24",
      "value": "FT-RWT13521",
      "assigner": {
        "identifier": {
          "system": "https://fhir.nhs.uk/Id/ods-organization-code",
          "value": "RAX"
        }
      }
    }
  }
```

<a name="status"></a>
<h4 class='additional-Guidance-Submenu'> status </h4>
Used to mark the completeness of a given family member's clinical history. If the history of a family member is expected but no history could be obtained, this  element SHOULD be filled with 'health-unknown'.

Assertions regarding absence of relevant history SHOULD follow guidance within the [HL7 FHIR R4 FamilyMemberHistory resource](http://hl7.org/fhir/R4/familymemberhistory.html#9.4.2.4)

```json
"status": "completed",
```

<a name="patient"></a>
<h4 class='additional-Guidance-Submenu'> patient </h4>
SHALL be present. Reference to the associated proband Patient for which this family history is being obtained. This MAY be through a resource reference if the ID on the central service is known (or provided within the transaction bundle) or through NHS number where this is known and has been traced through PDS

```json
"subject": {
        "reference": "Patient/Patient-MeirLieberman-Example",
        "identifier": {
            "system": "https://fhir.nhs.uk/Id/nhs-number",
            "value": "9449307873"
        }
    }
```

<a name="relationship"></a>
<h4 class='additional-Guidance-Submenu'> relationship </h4>
SHALL be present. Relationship between the person the FamilyMemberHistory references and the proband Patient. Clinical histories for each family member are expected to be recorded in separate FamilyMemberHistory resources. If multiple resources are required, both FamilyMemberHistory and related clinical artifacts such as Condition/Observation resources, these MAY be contained within a List resource to improve readability.

```json
"relationship": {
        "coding":  [
            {
                "system": "http://terminology.hl7.org/CodeSystem/v3-RoleCode",
                "code": "PRN",
                "display": "parent"
            }
        ]
    }
```

---