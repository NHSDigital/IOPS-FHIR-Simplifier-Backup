---
topic: Acknowledgement Message Pattern
---
## Acknowledgement Message Pattern
For message flows, the use of MessageHeader FHIR resource has been implemented for all interactions. This section describes the use of MessageHeader and its proposed usage to help with different transactions. 

The FHIR MessageHeader Resource defines the characteristics of a message that can be shared between systems, including the type of event that initiates the message, the content to be transmitted and the response, if any, is requested. NHS Digital has Profiled this Resource to be used in injunction with MESH or using a direct REST API. The Profile contains an extension to carry a specific instruction for receivers of the message.

The current asset types that are used in the message definition are:

#### Profiles (StructureDefinitions)


- [MessageHeader & OperationOutcome](https://simplifier.net/guide/Acknowledgement-Framework/Home/FHIRAssets/Profiles.page.md?version=current)  

- [Extensions](https://simplifier.net/guide/Acknowledgement-Framework/Home/FHIRAssets/Extensions.page.md?version=current)
	

- CodeSystem and ValueSet:

    o	ValueSet 'UKCoreMessageEvent'

            o	System: value = https://fhir.hl7.org.uk/CodeSystem/UKCore-MessageEvent . 
            o	Codes to be used in Pathology: pathology-order, specimen-received, specimen-collected, pathology-result . 
            o	Scope: Profile MessageHeader
Note: This CodeSystem is currently retired. A discussion will need to take place as to how this CodeSystem can be used and what values should be added, as well as its retired status and visibility in UK Core.
	
	
-	ValueSet 'ResponseType'

        o	System: http://hl7.org/fhir/response-code
        o	Codes: https://simplifier.net/packages/hl7.fhir.r4.core/4.0.1/files/82857
        o	Scope: Profile MessageHeader

Note: This is only used when a responder provides a responses 

-	IssueSeverity

        o	System: http://hl7.org/fhir/issue-severity
        o	Codes: FHIR R4
        o	Scope: OperationOutcome

-	IssueType

        o	System: http://hl7.org/fhir/issue-type
        o	Codes: FHIR R4
        o	Scope: OperationOutcome

-	ResponseCode

        o   System:http://terminology.hl7.org/CodeSystem/operation-outcome
        o	Codes: Check link above. There would be more codes added to that and the URL yet to be added. For more information, please [check](https://simplifier.net/guide/Acknowledgement-Framework/Home/FHIRAssets/CodeSystems.page.md?version=current) 
        o	Scope: OperationOutcome
