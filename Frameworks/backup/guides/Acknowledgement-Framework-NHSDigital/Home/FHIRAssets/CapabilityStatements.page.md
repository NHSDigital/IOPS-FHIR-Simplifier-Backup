## {{page-title}}

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> The Acknowledgement Framework is currently a draft version. Please contact the <a href="mailto:interoperabilityteam@nhs.net?subject=Acknowledgement Framework">Interoperability Standards Team</a> if you are interested to discuss this solution for your use case.</div>

All systems that use the Acknowledgement Framework shall use the CapabilityStatement resource. There are three types of CapabilityStatement which is represented by the code value in **CapabilityStatement.kind**. The three types are **requirements**, **capability**, and **instance**. 

The Acknowledgement Framework will have a 'requirements' CapabilityStatement which implementers shall conform to. Implementers shall also create and conform to 'capability' and/or 'instance' CapabilityStatement resources where appropriate.

Below is what is proposed for the values of the 'requirements' CapabilityStatement for the Acknowledgement Framework.

Please note that we anticipate future changes to this proposed CapabilityStatement, in particular providing additional information for rest, messaging and document. 

### AcknowledgementFrameworkCapabilityStatement


| Element Id | Value | 
| ---------- | ----- |
| CapabilityStatement.url | *(blank - don't know yet)* |
| CapabilityStatement.version | *(blank - don't know yet)* |
| CapabilityStatement.name | acknowledement-framework |
| CapabilityStatement.title | Acknowledgement Framework |
| CapabilityStatement.status | draft |
| CapabilityStatement.experimental | true |
| CapabilityStatement.date | *(date of last change/approval)* |
| CapabilityStatement.publisher | NHS Digital |
| CapabilityStatement.contact.name | Interoperability Team |
| CapabilityStatement.contact.telecom.system | email |
| CapabilityStatement.contact.telecom.value | interoperabilityteam@nhs.net |
| CapabilityStatement.contact.telecom.use | work |
| CapabilityStatement.description | This Capability Statement supports the implementation of the Acknowledgement Framework |
| CapabilityStatement.useContext | *(blank)* |
| CapabilityStatement.jurisdiction.coding.system | urn:iso:std:iso:3166:-2 |
| CapabilityStatement.jurisdiction.coding.code | GB-ENG |
| CapabilityStatement.jurisdiction.coding.display | England |
| CapabilityStatement.purpose | The purpose of this Capability Statement is to provide high level requirements and information for systems that implements the Acknowlegdement Framework |
| CapabilityStatement.copyright | *(blank - don't know yet)* |
| CapabilityStatement.kind | requirements |
| CapabilityStatement.instantiates | *(blank)* |
| CapabilityStatement.imports | *(blank)* |
| CapabilityStatement.software | *(blank)* |
| CapabilityStatement.implementation | *(blank)* |
| CapabilityStatement.fhirVersion | 4.0.1 |
| CapabilityStatement.format | xml, json |
| CapabilityStatement.implementationGuide | (blank - don't know yet)
| CapabilityStatement.rest | *(blank)* |
| CapabilityStatement.messaging | *(blank)* |
| CapabilityStatement.document | *(blank)* |


