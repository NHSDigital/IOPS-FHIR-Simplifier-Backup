## {{page-title}}

We have defined a data model for the whole GP record that we are working through a clinical area at a time. 
This is illustrated in the diagram below:

{{ render: GP_Record_Clinical_Areas_Overview.png }}

In the diagram each of the boxes with a blue outline represents a clinical area. 
These each contain 1 or more boxes representing FHIR&reg; resources. 
The FHIR resource boxes are colour coded:

* Green - are resources that are defined for GP Connect use in this version of the specification
* Blue - are resources that have yet to have their GP Connect usage defined

The clinical areas that are contained in the larger box on the right-hand side, labelled 'Clinical Item', are the clinical areas in which pieces of clinical information are held. 
The clinical areas on the left of the diagram will be used to model the way the clinical items are viewed, organised and managed in GP systems. 
The aim being that data can be reproduced in consumer interfaces in a way that maintains the context of the data and most accurately communicates the meaning that was intended by the clinician who created it.
