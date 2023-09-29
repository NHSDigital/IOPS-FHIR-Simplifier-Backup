## {{page-title}}


### Scope 
The scope of this document is all Implementation guides hosted on the NHS Digital Organization Simplifier account regardless of who produces them. It does not apply to any IG hosted on the HL7 organization Simplifier account. 



### Overview 
This document details the rules that **SHALL** be followed when producing NHS Digital FHIR Implementation Guides (IGs). The purpose is to drive consistency and quality across the IGs produced by either IOPs or other NHS Digital teams. 



### Rationale for Document 
NHS Digital has stated it is a “centre of excellence” and as such we use and follow accepted standard processes and best standards for our programmes. The current FHIR IG approach although not perfect, is a mature process which works and ensures conformance with the FHIR standard and the HL7 UK community process which is something NHS Digital must support as a key part of our standards delivery.   



### What is a FHIR IG
A FHIR IG (Implementation Guide) is the accepted way of documenting implementation guidance for FHIR which is used by all the major FHIR implementing countries and is defined in the FHIR standard as: 

“An implementation guide (IG) is a set of rules about how FHIR resources are used (or should be used) to solve a particular problem, with associated documentation to support and clarify the usage”. 

It is based on the FHIR ImplementationGuide resource: 

“The ImplementationGuide resource is a single resource that defines the logical content of the IG, along with the important entry pages into the publication, so that the logical package that the IG represents, so that the contents are computable.” 

“In particular, validators are able to use the ImplementationGuide resource to validate content against the implementation guide as a whole. The significant conformance expectation introduced by the ImplementationGuide resource is the idea of Default Profiles. Implementations may conform to multiple implementation guides at once.” 

FHIR IGs are usually published as a set of HTML pages and associated FHIR assets. 

The use of IGs is recommended by the HL7 and HL7 UK Community process. 



### Why use FHIR IGs 
FHIR IGs are the accepted way that FHIR specifications are published. Some of the major vendors will be implementing FHIR in more than one province / country. For example, they will be implementing US Core which is an IG and therefore the UK Core follows the same accepted format i.e., is an IG. NHS Digital must also follow this accepted way of publication for its FHIR specifications to align with the rest of the world and to avoid deviation from the standard or “reinventing the wheel”. 



### FHIR Specification Audience  
The audience of a FHIR IG is large and varied some of typical consumers (in no particular order) are listed below: 

- FHIR experts 
- Developers 
- Clinicians  
- Solution Architects 
- Technical Architects  
- Clinical Informaticians
- Business Analysts
- Project Managers
- Interoperability Managers 

Each of these may have a preferred view of the FHIR specification and therefore it is acceptable and probably desirable to publish different views of the same IG content for a specific audience, however it is important to have only one version of the source content which **SHALL** be the FHIR IG with other views created or generated from that source. 



### Use of Simplifier  
IOPS and HL7 UK use the Simplifier platform for some of the following reasons: 
- Enables FHIR compliant IGs to be produced.
- Allows validation of IGs against the FHIR standard. 
- Allows the creation and maintenance of NPM Packages with full version control. 
- Supports publication of packages to the FHIR Package Registry (https://registry.fhir.org/), which is highly desirable to share the packages with the FHIR community locally and internationally.
- Enables derived IGs to be created and validated with full dependency tracking.
- Supports version control for all FHIR assets including rendering of multiple versions of a given asset for a given IG version.
- Supports custom templates and stylesheets.



### Use of packages 
The accepted FHIR approach for implementation of FHIR and validation of implementations is the use of NPM packages. This approach is endorsed by all the major UK vendors for FHIR implementations. All NHS Digital IGs **SHALL** use NPM packages.   



#### HL7 Packages 
Excerpt from the FHIR standard below:
“One use of Packages is to bundle together all the FHIR artefacts in an Implementation Guide to make them easier to locate and download. More specifically, a package will contain the FHIR resources for a specific version of an Implementation Guide - indeed, it was the complexity of versioning Implementation Guides and FHIR resources that led to the adoption of packages. It will not, however, contain the other components of an Implementation Guide such as the documentation or the IG layout (menus, images, summary pages etc). So, a package is stable, versioned collection of resources - often those from an Implementation Guide.”



### Conformance Statement  
It is a FHIR requirement to use a CapabilityStatement to define an implementations capability. All NHS Digital IGs **SHALL** include a CapabilityStatement and associated guidance. 



### HL7 UK Community Process 
All NHS Digital IGs **SHALL** comply with the HL7 UK community process   



### IG Design Rules 
This section details the design rules that **SHALL** be followed by any creator of an IG hosted in the NHS Digital Simplifier Organization account. 



#### Use of Stylesheets and Templates:
- All IGs **SHALL** only use an approved version of the IG stylesheet.  
- The latest version of the stylesheet SHOULD be adopted wherever possible. 
- Custom stylesheets **SHALL NOT** be used by any IG creator. 
- New IGs **SHALL** conform to the latest approved template.
- Pre-existing IGs **SHALL** conform to an approved template.
- Pre-existing IGs **SHOULD** conform to the latest approved template. 
- Changes to stylesheets **SHALL** be requested and approved before implementing in any Simplifier project. 



#### Requesting Stylesheet Changes 
All changes for a change to the IG stylesheet **SHALL** be requested via Simplifier issue tracking. This **SHALL** be done on the Current Template project. 



#### Approval of Stylesheet Changes 
All requests for change   



#### Simplifier Projects 
There **SHALL** be two projects for IG templates and stylesheets: 
- Current Template 
- Development Template 



#### Current Template Project  
This will contain the current stylesheet and template that **SHALL** be used as the basis for creation of all IGs. These **SHALL** be clearly marked with version numbers to indicate they are the latest versions.    



#### Development Template Project 
This will contain any stylesheets and templates that are in development and **SHALL NOT** be used as the basis for creation of any IGs. These **SHALL** be clearly marked with version numbers to indicate they are new versions. 



#### Updating Approved Template/Stylesheet    
The development stylesheet and/or template **SHALL** be approved by the IOPS Design Authority before it is released to the current template project. The development stylesheet and/or template **SHALL NOT** be used for development or creation of any IG except for testing and review in the development template project. Release of and development or the stylesheet will usually be done in maintenance sprints but there may be a requirement to do bug fixes etc.   



### Stylesheet Versioning 
- All stylesheets used **SHALL** be versioned. 
- Any change to the stylesheet **SHALL** increment the version of the stylesheet.



### NHS Digital IG Style Guide 
- All IGs **SHALL** comply with the NHS Digital style guide. 



### Review of IGs 
This section gives the overview rules for preparing for a review: 
- All IGs **SHALL** be reviewed prior to sharing or releasing to an external audience.  
- Creators of IGs **SHALL NOT** submit IGs for review that do not conform to the rules.  
- Reviewers of IGs **SHALL** discontinue the review immediately if the IG is found to not conform to the rules.   

FHIR IGs **SHALL** conform to certain rules see below: 
All NHS Digital IGs **SHALL** comply with the following:  
- <a href="https://confluence.hl7.org/display/HL7UK/HL7+UK+FHIR+Community+Process" target="_blank">HL7 UK community process</a>

All NHS Digital IGs SHOULD comply with the following: 
- <a href="https://confluence.hl7.org/display/FHIR/FHIR+Implementation+Guide+Publishing+Requirements" target="_blank">The HL7 Publishing requirements</a>

There is also guidance on how to <a href="https://confluence.hl7.org/display/FHIR/FHIR+IG+Review" target="_blank">review</a> an IG. 


     