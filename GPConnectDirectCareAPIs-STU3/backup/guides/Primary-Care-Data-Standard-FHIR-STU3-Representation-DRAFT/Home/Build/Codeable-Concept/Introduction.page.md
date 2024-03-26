## {{page-title}}
The CodeableConcept is one of the most important data items in HL7’s Fast Healthcare
Interoperability Resources (FHIR®) and is defined in the FHIR® specification as:

“a value that is usually supplied by providing a reference to one or more
terminologies or ontologies, but may also be defined by the provision of
text. This is a common pattern in healthcare data.”
http://hl7.org/fhir/stu3/datatypes.html#CodeableConcept

NHS Digital has introduced an extension to the base CodeableConcept data type to carry
information chosen by the end user (or held in the end user’s system) that originated from
the SNOMED CT terminology and cannot be expressed using just the SNOMED CT
preferred term and concept id.

Aimed at FHIR developers, this document shows you how to process the CodeableConcept,
including:
- How to populate the code
- How to receive the code
- How to render the code to a user
- How to deal with multiple codes
- What to do if the coded data is not understood by receiving systems

The extent of the CodeableConcept data type (including the Extension-coding-sctdescid
extension) is as follows:
```xml
<code>
    <coding>
        <extension>
            <url value="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-codingsctdescid" />
            <extension>
                <url value="descriptionId" />
                <valueId value="" />
            </extension>
            <extension>
                <url value="descriptionDisplay" />
                <valueString value="" />
            </extension>
        </extension>
        <code value="" />
        <display value="" />
        <system value="" />
        <version value="" />
        <userSelected value="" />
    </coding>
</code>
```