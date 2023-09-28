## StructureDefinition Extension-UKCore-CodingSCTDescId

The description ID and display term for a SNOMED CT concept.  The descriptionId and its associated display term are important to enable the representation of the exact term that was entered by the clinician that recorded the data, or the exact term that a legacy code e.g. a Read v2 code has been translated to using an assured mapping table.

### Purpose
This extension extends the Coding datatype to support the exchange of the selected description ID and display term for a SNOMED CT concept, which is currently not supported by the FHIR standard.

### Guidance
<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4>This extension is NOT hardcoded in any UK Core profiles due to technical issues as this extension is only used when the terminology used is SNOMED CT. This makes the hardcoding in the profiles as not desirable and liable to cause confusion on Extensible coded data elements without adding multiple slices and therefore was deemed as not a good technical solution.</h4>
</div>


<table id="assets">
<tr>
<th colspan="2">Context of Use</th>
</tr>
<tr>
<td>Use on data type</td>
<td>CodeableConcept</td>
</tr>
</table>
<br/>


<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Snapshot View')">Snapshot View</button>
  <button class="tablinks" onclick="openTab(event, 'Differential View')">Differential View</button>
  <button class="tablinks" onclick="openTab(event, 'Hybrid View')">Hybrid View</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
   <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
</div>

<div id="Snapshot View" class="tabcontent" style="display:block">
  <h3>Snapshot View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId, snapshot}}
</div>

<div id="Differential View" class="tabcontent">
  <h3>Differential View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId, diff}}
</div>

<div id="Hybrid View" class="tabcontent">
  <h3>Hybrid View</h3>
{{tree:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId, hybrid}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId, snapshot}}
</div>
<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
An example to illustrate the extension of adding a SNOMED CT description Id.</br>
{{pagelink:ExampleUKCore-Condition-CodingSCTDescId-Index}}
</div>
<br/>

### Extension Additional Guidance

This extension to the base CodeableConcept data type has been introduced to carry information chosen by the end user (or held in the end user’s system) that originated from the SNOMED CT terminology and cannot be expressed using just the SNOMED CT preferred term and concept id.

Aimed at FHIR developers, this guidance will show how to process the CodeableConcept, including:

* How to populate the code
* How to receive the code
* How to render the code to a user
* How to deal with multiple codes
* What to do if the coded data is not understood by receiving systems

The extent of the CodeableConcept data type (including the Extension-coding-sctdescid extension) is as follows:


XML
``` xml
<code>
	<coding>
		<extension url="https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId">
			<extension url="descriptionId">
				<valueId value=""/>
			</extension>
			<extension url="descriptionDisplay">
				<valueString value=""/>
			</extension>
		</extension>
		<code value=""/>
		<display value=""/>
		<system value=""/>
		<version value=""/>
		<userSelected value=""/>
	</coding>
	<text/>
</code
```

#### Description of elements (in terms of SNOMED CT)

| Element                              | Description                                                                               |
|--------------------------------------|-------------------------------------------------------------------------------------------|
| `code`                               | The wrapper element for the CodeableConcept.                                              |
| `coding`                             | The wrapper element for the coded part of the CodeableConcept.                            |
| `extension`                          | The wrapper element for the SNOMED description extension.                                 |
| `extension url="descriptionId"`      | The wrapper for the SNOMED CT description identifier.                                     |
| `valueId`                   | Holds the SNOMED CT description identifier.                                               |
| `extension url="descriptionDisplay"` | The wrapper for the SNOMED CT description display.                                        |
| `valueString`               | Holds the SNOMED CT description display.                                                  |
| `code`                      | Holds the SNOMED CT concept identifier.                                                   |
| `display`                   | Holds the SNOMED CT concept display.                                                      |
| `system`                    | Holds the SNOMED CT system identifier  `http://snomed.info/sct`                           |
| `version`                   | Is not used for SNOMED CT.                                                                |
| `userSelected`              | Indicates that this concept was chosen by the user.                                       |
| `text`                               | Represents the text that was originally displayed to the user when the code was recorded. |

#### Populating the CodeableConcept

This section shows you how to populate each field where the code carried is a SNOMED CT code and where it’s not a SNOMED CT code. It also includes population scenarios with examples.

##### Field by field population guidance

| Level | Element     | Directions                                                                                                                                                            |
|-------
| 1   | `coding` (SNOMED CT) | Populate this group if a SNOMED CT concept id is stored for the item.                                                                                                                                         |
| 2   | `system`     | Set to `http://snomed.info/sct`.                                                                                                                                                    |
| 2   | `code`     | The SNOMED CT concept id stored for the item.                                                                                                                                                 |
| 2   | `display`    | The text of the current preferred term of the SNOMED CT concept id according to the current NHS Realm Language Reference Sets.<br>The text of the preferred term of the SNOMED CT concept id.<br>The preferred term is the description specified for the concept in the NHS realm description subset. The preferred term for a concept may change over time. The sending system should determine the current preferred term for the concept.                               |
| 2   |  `extension url="descriptionId"` | The SNOMED CT descriptionId recorded with the item. Only populated if a descriptionId exists.                                                                                                                               |
| 2   |  `extension url="descriptionDisplay"` | The text of the description id. Only populated if a descriptionId exists and there is no need to populate this field if the text is lexically identical to the text in coding.display.                                                                                                 |
| 2   | `userSelected`   | Set to `true` if a user selected the SNOMED CT Code when creating/updating this item. If this is `false` then this element MUST not be populated by the supplying system. <br>For consuming systems the absence of this element therefore indicates that it is `false`.                                                                        |
| 1   | `coding` (other)   | Populate this group if a clinical code other than SNOMED CT is stored for the item. If there are multiple codes (that is,. the item has been translated multiple times) there is a group entry per code.                                                                                            |
| 2   | `system`     | The identification of the code system that defines the meaning of the symbol in the code.                                                                                                                                 |
| 2   | `code`     | The clinical code associated with the item.                                                                                                                                                 |
| 2   | `display`    | The longest character length variant text associated with the current preferred term for the clinical code.                                                                                                                           |
| 2   |  `extension url="descriptionId"`  | Do not populate (SNOMED CT only).                                                                                                                                                     |
| 2   |`extension url="descriptionDisplay"` | Do not populate (SNOMED CT only).                                                                                                                                                     |
| 2   | `userSelected`   | Set to `true` if a user selected this code when creating/updating this item. If this is `false` then this element MUST not be populated by the supplying system. <br>For consuming systems the absence of this element therefore indicates that it is `false`.                                                                          |
| 1   | `text`     | The original text selected/manually entered by the user for the item. Only populate when there is no user selected translation set with a display or descriptionDisplay recorded. <br>If the text displayed to the user when they entered the code on the system is not lexically identical to the term of the code then the displayed text must be populated here. <br><b>Note:</b> This occurs when either the original entry was not coded or the original coding has been lost. |

#### Sending dm+d codes 

Where a supplier is using the dm+d codes which does not contain any data at the descriptionId level, then we would not expect the descriptionId extension to be populated.
Where the descriptionId is available then this SHALL be included. 

The example below demonstrates how a dm+d code should be sent where there is no descriptionId available.


XML
``` xml
<code>
  <coding>
   <code value="323509004"/>                     
   <display value="Amoxicillin 250mg capsules"/>     
   <system value="https://dmd.nhs.uk/"/>
   <userSelected value="true"/>
  </coding>
</code>
```
JSON
``` json
{
    "code": {
        "coding": [{
            "code": "323509004",
            "display": "Amoxicillin 250mg capsules",
            "system": "https://dmd.nhs.uk/",
            "userSelected": true
        }]
    }
}
```

***

#### Sending a SNOMED CT concept with its associated preferred term 

When sending a SNOMED CT concept id with its preferred term and the descriptionId is known, then code.coding.code, code.coding.system and code.coding.extension.descriptionId SHALL be populated. Where the descriptionId is not known then the codeable concept MAY be sent without the descriptionId.

In the example below, the descriptionId is populated with the descriptionId for the preferred term, but there is no descriptionDisplay as the concept id was entered by the user and the preferred term was displayed to them when it was added.

XML
``` xml
<code>
  <coding>
      <extension url="https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId">
        <extension url="descriptionId">
          <valueId value="37436014"/>
        </extension>
      </extension>
    <code value="22298006"/>                     
    <display value="Myocardial infarction"/>     
    <system value="http://snomed.info/sct"/>
    <userSelected value="true"/>
  </coding>
</code>
```

JSON
``` json
{
    "code": {
        "coding": [{
            "extension": [{
				"url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId",
				"extension": [{
					"url": "descriptionId",
					"valueId": "37436014"
				}]
			}],
            "code": "22298006",
            "display": "Myocardial infarction",
            "system": "http://snomed.info/sct",
            "userSelected": true

        }]
    }
}
```

***

#### Sending a concept where the coding system and code is unknown 

In the exceptional case that the code is not known, then the code.text element can be populated without the need to populate a coding element.

XML
``` xml
<code>
   <text>Myocardial infarction</text> 
</code>

```

JSON
``` json
{
	"code": {
		"text": "Myocardial infarction"
	}
}

```


#### Sending a description id that is not the preferred term ###
In this case, the description id represents a term that is different from the preferred term and therefore the description will be different from that used to populate the code.coding.display element. Therefore the extension for descriptionDisplay shall be populated with the term corresponding to the descriptionId.

XML
``` xml
<code>
   <coding>
     <extension url="https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId">
       <extension url="descriptionId">
         <valueId value="37443015"/>
       </extension>
       <extension url="descriptionDisplay">
         <valueString value="Heart attack"/>
       </extension>
     </extension>
     <code value="22298006"/>
     <display value="Myocardial infarction"/>
     <system value="http://snomed.info/sct"/>
     <userSelected value="true"/>
   </coding>
</code>
```

JSON
``` json
{
    "code": {
        "coding": [{
            "extension": {
                "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId",
                "extension": [{
                        "url": "descriptionId",
                        "valueId": "37443015"
                    },
                    {
                        "url": "descriptionDisplay",
                        "valueString": "Heart attack"
                    }
                ]
            },
            "code": "22298006",
            "display": "Myocardial infarction",
            "system": "http://snomed.info/sct",
            "userSelected": true

        }]
    }
}
```


#### Sending a translation set 

In the case where the code was entered into the clinical system using a legacy coding system, the code will have been mapped to a SNOMED CT translation. 

However, in SNOMED CT, all concept ids always have more than one associated description: all have at least one fully specified name and at least one additional associated synonym. Of these, exactly one fully specified name and one synonym will be declared to be “preferred” at any point in time within a Realm Language Reference Set, but which terms are designated “preferred” can and does change over time.

Therefore, in most cases where such mappings have been created, they will have been mapped to an explicit pairing of one SNOMED CT concept id and one of its legitimate description ids. The particular descriptionId selected may also correspond to the preferred term but often does not.

Exceptionally, mappings may correspond to a SNOMED CT concept id only and so no particular description is declared in the map. In these cases the description originally entered by the clinician in the legacy coding system is considered to be the clinically relevant text.

 XML
 ``` xml
<code>
   <coding>
       <code value="44I4.00"/>
       <display value="Serum potassium"/>
       <system value="http://read.info/readv2"/>
       <userSelected value="true"/>
       <!--flags the coding originally actually selected by the user -->
   </coding>
   <coding>
     <extension url="https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId">
       <extension url="descriptionId">
         <valueId value="2573011000000117"/>
       </extension>
     </extension>
     <system value="http://snomed.info/sct"/>
     <code value="1000651000000109”/>
     <display value="Serum potassium level"/>
   </coding>
   <text>Serum potassium</text>
   <!-- what the user saw on screen, from a data entry template -->
</code>

 ```

 JSON
 ``` json
{
    "code": {
        "coding": [{
		    "extension": [{
				"url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId",
				"extension": [{
					"url": "descriptionId",
				 	"valueId": "2573011000000117"
			    	  }]
			    }],
                   }
               ],
 
                "code": "44I4.00",
                "display": "Serum potassium",
                "system": "http://read.info/readv2",
                "userSelected": true
            },
            {
                "system": "http://snomed.info/sct",
                "code": "1000651000000109"
	          "display": "Serum potassium level",
        "text": "Serum potassium"
    }
}

 ```

XML
``` xml
<code>
   <coding>
       <code value="B76..14"/> <!— term code = 14 ie not V2 Preferred term -->
       <display value="Mole of skin"/> <!— text for V2 term code = 14 -->
       <system value="http://read.info/readv2"/>
       <userSelected value="true"/>  <!-- coding actually selected by user -->
   </coding>
   <coding>
       <code value="X78Uv"/> <!— no term code, so CTV3 PT is implied? -->
       <display value="Benign melanocytic naevus of skin"/> <!— text of V3 PT -->
       <system value="http://read.info/ctv3"/>
   </coding>
   <coding>
     <extension url="https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId">
        <extension url="descriptionId">
           <valueId value="1787065011"/> <!— not the SNOMED PT -->
        </extension>
       <extension url="descriptionDisplay">
         <valueString value="Mole of skin"/> <!— text for id = 1787065011 -->
       </extension>
     </extension>
     <system value="http://snomed.info/sct"/>
     <code value="400010006”/> <!— SNOMED conceptId -->
     <display value="Melanocytic naevus of skin"/> <!— text of SNOMED PT -->
   </coding>
   <text>Moles</text> <!-- what user saw on screen, from data entry template -->
</code>

```

JSON
``` json
{
    "code": {
        "coding": [{
                "code": "B76..14",
                "display": "Mole of skin",
                "system": "http://read.info/readv2",
                "userSelected": true
            },
            {
                "code": "X78Uv",
                "display": "Benign melanocytic naevus of skin",
                "system": "http://read.info/ctv3",
            },
            {
                "system": "http://snomed.info/sct",
                "code": "400010006"
	          "display": " Melanocytic naevus of skin",
		    "extension": [{
				"url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId",
				"extension": [{
					"url": "descriptionId",
					"valueId": "1787065011"				},
                    {
                        "url": "descriptionDisplay",
                        "valueString": "Mole of skin"
                    }]
			}],
            }
        ],
        "text": "Moles"
    }
}

```


#### Rules for populating legacy coding 

##### Read Code 

All Read Codes should be represented using a full five characters.
- Where 4-byte codes are used these must be preceded by a full-stop as in the NHS Clinical Terms superset  (e.g. 4-byte code "6521" is represented as ".6521").
- Trailing full-stops are significant and must be included (e.g. "H43" is not a valid Read Code and must be represented in full as "H43..").
    - Care should be taken in any environment where a Read Code may have been subjected to auto-correction because:
        - Upper/lower case is significant
        - Conversion of a sequence of three full-stops "..." to a single "…" (ASCII Hex "85" Unicode Hex "2026") special character occurs in some environments and creates invalid Read Codes.

##### Read Code version 2 term code 

Read Codes Version 2 uses a "Term Code" to distinguish between some alternative terms associated with the same Read Code. A Term Code is represented as a two digit string and is only unique within the context of a single Read Code. 
 
It is now widely recognised that many of the terms associated with a Read Code are not true synonyms. This issue was partially resolved in NHS Clinical Terms Version 3 and further disambiguation has occurred in development of SNOMED Clinical Terms. However, in the meantime where Term Codes are stored these should be communicated with the Read Code.
 
A Read Code + Term Code combination is communicated as a single seven character code. Thus the code "7001200" represents the Term Code "00" associated with the Read Code "70012".
 
Note that this specification requires the term to be conveyed in the message in addition to any coded representation. Therefore, safe communication is not dependent on use of the Term Code in all systems. Therefore, a sending system that does not support Term Codes for a particular item of information should not send a Term Code. Similarly a receiving system that does not support Term Code storage may ignore the Term Code when constructing a record entry. However, where a sending system stores the Term Code this should be included in the message and where a receiving system stores the Term Code this should be retrieved from the message.

##### NHS Clinical Terms Version 3 – Term Id 

In NHS Clinical Terms Version 3 the TermId is a five character string that uniquely identifies an associated term (or set of two or three terms of alternative lengths). Although it is globally unique it says nothing about the associated concept and thus must be combined with the Read Code. There are no plans to use the TermID in NHS Clinical Terms Version 3 and thus inclusion of TermId is not permitted. 


#### Sending a description id NOT in the UK Edition, but for a concept id that IS in the UK Edition 

Includes the case where the description id is locally declared to be the preferred term.

XML
``` xml
<code>
   <coding>
     <extension url="https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId">
       <extension url="descriptionId”>
         <valueId value="787121000006116"/> 
         <!-- descriptionId from EMIS namespace -->
       </extension>
       <extension url="descriptionDisplay">
          <valueString value="Ideal weight"/>
       </extension>
     </extension>
     <code value="170804003"/>
     <!-- conceptId from SNOMED International CORE -->
     <display value="Ideal body weight"/>
     <system value="http://snomed.info/sct"/>
     <userSelected value="true"/>
   </coding>
</code>

```


JSON
``` json
{
    "code": {
        "coding": {
            "extension": [{
                "url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId",
                "extension": [{
                    "url": "descriptionId",
                    "valueId": "787121000006116"
                }, {
                    "url": "descriptionDisplay",
                    "valueString": "Ideal weight"
                }]
            }],
            "code": "170804003",
            "display": "Ideal body weight",
            "system": "http://snomed.info/sct",
            "userSelected": true
        }
    }
}

```


### Sending a description id and concept id where NEITHER is in the UK Edition 

XML
``` xml
<code>
   <coding>
     <extension url="https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId">
       <extension url="descriptionId">
          <valueId value="253790221000087110"/>  
          <!— from Canadian extension -->
       </extension>
       <extension url="descriptionDisplay”>
          <valueString value="Use of illicit drugs unknown"/>   
          <!-- synonym from Canadian extension -->
       </extension>
     </extension>
     <code value="186782131000087106"/>                      
     <!-- conceptId from Canadian extension -->
     <display value="Use of illicit type drug unknown"/>
     <!-- preferred term from Canadian extension -->
     <system value="http://snomed.info/sct"/>
     <userSelected value="true"/>
   </coding>
   <text> Not known whether uses illicit drugs</text>           
   <!-- what the user saw on screen, from a data entry template -->
</code>

```

JSON
``` json
{
	"code": {
		"coding": {
			"extension": {
				"url": "https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId",
				"extension": [
					{
						"url": "descriptionId",
						"valueId": "253790221000087110"
					},
					{
						"url": "descriptionDisplay",
						"valueString": "Use of illicit drugs unknown"
					}
				]
			},
			"code": "186782131000087106",
			"display": "Use of illicit type drug unknown",
			"system": "http://snomed.info/sct",
              "userSelected": "true"
		},
		"text": " Not known whether uses illicit drugs"
	}
}

```


#### Processing data from a CodeableConcept

##### Degradation 

Degradation is a process used in clinical systems' interoperability for dealing with codes that are not understood by receiving systems. When codes are degraded the original text entered by a user is then associated with an appropriate degrade code. For example, a drug allergy code that is not understood will be associated with a code for ‘Degraded drug allergy’.

##### Why and how does it happen? 

When clinical codes move between systems, sometimes the receiving system may not understand all the clinical codes that it was sent. This can be for a number of reasons:

- The receiving system may use a different terminology than the sending system. An example of a place in which this happens is in primary care where TPP SystmOne uses Clinical Terms Version 3 and EMIS Web uses Read version 2.

- Clinical systems may be using different releases of the same terminology. In the UK, terminologies are updated regularly, usually 6 monthly. When they are updated new codes are added and old codes deprecated. If one system updates before another then for a period it may contain new codes that systems using an older version do not understand.

- SNOMED CT has an extension mechanism that allows SNOMED CT to be customized usually be adding additional concepts and descriptions. So sending systems may have added content that is not available on the receiving system. See examples 6 and 7 on how messages are populated with extension data.

There may be many other reasons that codes are not understood between systems but the above are some of the most common reasons. Here they are intended to illustrate that degrades happen but are not intended to be an exhaustive list.

##### Why do we need a process to deal with it? 

Where codes are not understood by clinical systems, having a degrade process enables us to improve interoperability and related functionality. Having appropriate degrade codes enables us to retain the structure and semantics. For example, degraded allergies appear in allergies view, medication degrades appear in medication module.

Some examples of how this can work are:

- Where allergies are degraded, associating the item that was not understood with an allergy degrade code that the clinical system understands can enable it to trigger (for example) additional prescribing safety decision support systems and workflows.

- Where medication codes are not understood and the data item is associated with a medication degrade code, the information can be displayed alongside all other medications in the clinical system.

##### What do degrades look like? 

Where items are degraded, how they appear can vary depending on how a clinical system chooses to display them to a user. In many cases, depending on whether the actual code is displayed to the user, the degrade may appear to be similar to any code natively added in a system.

When they are then exported into a FHIR resource they will be exported as a degrade code with the text originally entered by the user in the code.text element.

##### FHIR message examples 

Example of a degraded medication:

XML
``` xml
<code>
  <coding>
    <display>Transfer-degraded medication entry</display>
    <code>196421000000109</code>
    <system>http://snomed.info/sct</system>
  </coding>
  <text>Aspirin 75mg dispersible tablet</text>
</code>

```


JSON
``` json
{
    "code": {
        "coding": [{
            "display": "Transfer-degraded medication entry",
            "code": "196421000000109",
            "system": "http://snomed.info/sct"
        }],
        "text": "Aspirin 75mg dispersible tablet"
    }
}

```

Example of a degraded drug allergy:


XML
``` xml
<code>
  <coding>
    <display>Transfer-degraded drug allergy</display>
    <code>196461000000101</code>
    <system>http://snomed.info/sct</system>
  </coding>
  <text>Amoxicillin 250mg capsules</text>
</code>
```

JSON
``` json
{
    "code": {
        "coding": [{
            "display": "Transfer-degraded drug allergy",
            "code": "196461000000101",
            "system": "http://snomed.info/sct"
        }],
        "text": "Amoxicillin 250mg capsules"
    }
}

```


#### Clinical codes 

#### Storage 

When storing the item, the receiving system may choose to store any or all of the clinical codes associated with the item.

However, where the system supports SNOMED CT codes it MUST store any SNOMED CT codes associated with the item.

Where the receiving system does not understand any of the supplied coding.systems which a coding has been associated with the item (or no clinical codes were supplied), it may choose to record the item under a degraded code. The appropriate SNOMED degrade code should be used within the system to store the code.

<table id="assets">
<tr>
<th colspan="2">The following codes are available in SNOMED to represent degraded items and can be used when populating FHIR resources.</th>
</tr>
<tr>
<td>Degraded Drug Allergies</td>
<td>196461000000101 - Transfer-degraded drug allergy</td>
</tr>
<tr>
<td>Degraded Non-Drug Allergies</td>
<td>196471000000108 - Transfer-degraded non-drug allergy</td>
</tr>
<tr>
<td>Degraded Medications</td>
<td>196421000000109 - Transfer-degraded medication entry</td>
</tr>
<tr>
<td>Degraded Plan</td>
<td>196451000000104 - Transfer-degraded plan</td>
</tr>
<tr>
<td>Degraded Referral</td>
<td>196431000000106 - Transfer-degraded referral</td>
</tr>
<tr>
<td>Degraded Request</td>
<td>196441000000102 - Transfer-degraded request</td>
</tr>
<tr>
<td>Other degrade</td>
<td>196411000000103 - Transfer-degraded record entry</td>
</tr>
</table>

<br/>
Where an item that is being degraded is contained within a resource that infers a particular type of degrade then the appropriate code shall be used e.g. a code in a FHIR medication resource shall use the ‘Degraded medication’ code. 

Clinical systems MUST NOT attempt to infer a particular type of degrade code where there is no clear indication that a specific type of data has been degraded. In these scenarios the ‘Transfer degraded record entry’ code shall be used.


#### Display 

When displaying the item to end users, it is the choice of the receiving system to design their system and user experience in a safe manner that best suits their users.

#### Propagation 

When propagating coded data to another system, the system which received the item may choose which clinical codes to include when sending the item.

If a receiving system receives a SNOMED code that it does not understand it COULD store this code and propagate it onwards if the data is exported. If systems decide to do this they should consider what would happen if the data item is changed/edited.

Note: Whilst it is the receiving system’s decision which clinical codes are appropriate for it to store, NHS England requires that SNOMED CT is supported across the entire NHS estate by April 2020.

***

### Original term text

#### Storage 

When processing an item, the receiving system MUST always store the original term text of the item. That is, the text chosen/manually entered by the clinician/user to describe the item they are recording. Failure to do this could result in the intended meaning of the item being altered.

The original term text will be available in one of the following fields in order of descending priority:
1.	text
2.	coding.descriptionDisplay where userSelected = TRUE (or is unpopulated, and only one coding element is present)
3.	coding.display where userSelected = TRUE (or is unpopulated, and only one coding element is present)

Where the receiving system can derive the original term text from the clinical code and the derived text is lexically identical to the original term text, then the receiving system is not required to store the text separately.

However, where the system supports SNOMED CT codes it MUST store any SNOMED CT codes associated with the item where the userSelected is set to ‘TRUE’ and propagate these onward in any future export of the data. As noted in section 3.1, some SNOMED CT codes received may be from a release or extension of SNOMED not available on the receiving system.

#### Display 

When displaying an item to end users, the receiving system MUST always display the original term text of the item.

#### Propagation ####

When propagating an item to another system, the receiving system MUST always include the original term text of the item.

---


