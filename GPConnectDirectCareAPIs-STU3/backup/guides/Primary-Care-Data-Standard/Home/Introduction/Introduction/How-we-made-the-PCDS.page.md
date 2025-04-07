## {{page-title}}

### Our goal in mind:
To create a human-readable data standard for GP data & interoperability standard for data sharing:

{{render:PCDS Process.png}}

This diagram shows step-by-step the processes of how we made the PCDS. 

1.	Research the specific use-cases for each data standard and how it can relate to the PCDS.
1.	Using each example data standard in step 1, go through each profile, e.g. allergies, go through the GP data model, define the cardinality, data types and FHIR target and then add the needed SNOMED codes, or NHS data dictionary, and then we compare it to the other standards. 
    a.	Sometimes we started with CIS data model and then compared it to the GP Connect data model.
1.	First internal review with the team.
    a.	Reviewing the data
    a.	Accurate FHIR types
    a.	Accurate data types
1.	Second review is sign off by clinicians, data experts, etc. Similar review points of step 3.
1.	Getting it through front door teams, etc.
1.	Publishing the standard.

### Overview
The below image shows a high level overview of what sections are in the PCDS and which sections have been merged, due to either of the FHIR targets being similar.
{{render:PCDS Sections.png}}

Within these sections, we have used a variety of data types and included a link to an open source website containing information regarding what each of the data types are, and how they can be used. Each datatype has links within the PCDS but this is the resource that we have used: [DECOR-dataset](https://wiki.art-decor.org/index.php?title=DECOR-dataset) 
