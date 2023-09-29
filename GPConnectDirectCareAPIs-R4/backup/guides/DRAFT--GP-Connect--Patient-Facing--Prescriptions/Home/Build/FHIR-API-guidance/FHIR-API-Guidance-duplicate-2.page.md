## {{page-title}}

## Purpose

This site is intended for use by software developers looking to build a conformant GP Connect API interface using the FHIR&reg; standard, with a particular focus on FHIR specifics.

### Notational conventions

The keywords '**MUST**', '**MUST NOT**', '**REQUIRED**', '**SHALL**', '**SHALL NOT**', '**SHOULD**', '**SHOULD NOT**', '**RECOMMENDED**', '**MAY**', and '**OPTIONAL**' on this site are to be interpreted as described in [RFC 2119](https://www.ietf.org/rfc/rfc2119.txt).

## FHIR implementation guidance

The purpose of the implementation guide is to describe adaptations of the base FHIR specification specific for GP Connect First of Type (FoT) implementations. It therefore focuses mainly on any additional constraints and specialisations from the base specification that apply to GP Connect. The complete specification therefore comprises the base FHIR specification plus the constraints and specialisations described herein. Where there is a conflict between the base specification and this web page, this web page shall take precedence.

### FHIR overview

As outlined on the official [HL7&reg; FHIR](http://hl7.org/fhir/R4/) website:

> FHIR (Fast Health Interoperability Resources) is designed to enable information exchange to support the provision of healthcare in a wide variety of settings. The specification builds on and adapts modern, widely used RESTful practices to enable the provision of integrated healthcare across a wide range of teams and organisations.

### [FHIR timelines](https://hl7.org/fhir/directory.html)

STU3 is a pre-release version of FHIR standard and as such is expected to evolve and develop over time. NHS Digital expects FHIR clients and servers (developed as part of GP Connect) to be maintained and uplifted to newer versions of the FHIR&reg; standard as they become available and are staged into the GP Connect programme.

When a new release of the FHIR standard has been published for use NHS Digital will carry out an impact assessment of all FHIR resources used by the GP Connect API project to determine the impact of transitioning to the new FHIR release. Following this assessment, the FHIR resource library will be updated to include resources using this new release. NHS Digital will work with consumers and providers throughout this transition phase and are expected to maintain both versions of the FHIR release until it has been agreed that the old version can be deprecated.

### FHIR implementations

The Health Level Seven (HL7&reg;) International standards body maintains a list of open source FHIR implementations on its [Wiki](http://wiki.hl7.org/index.php?title=Open_Source_FHIR_implementations). Currently five FHIR server implementations and a number of client libraries are available as open source software. These are written in a variety of popular programming languages, such as Java, C#.NET, JavaScript and Python.

{% include tip.html content="NHS Digital strongly recommends that software vendors use (and contribute back to) an existing open source FHIR library to both help accelerate development and to grow/mature the open source FHIR ecosystem." %}
