## {{page-title}}

We believe ADPIE together with Clinical Pathway description provides very useful documentation for understanding interoperability requirements. This still supports domain or care setting data standards BUT interoperability appears to be better focused on support interactions and sharing records rather than implementing the data standards.

For example the diabetes use cases we have shown, are implementing https://theprsb.org/standards/diabetesstandards/ but this model is collected as required along several diabetes pathways. This is also true for https://theprsb.org/standards/social-prescribing-standard/ one of these, Physical Activity is also an early diabetes intervention (in the Wellness section).

We are seeing zero evidence that care providers solve either data standard with a single set of interoperability standards. In most cases are acutally solved with a mix of frameworks and interaction standards.


We are recommending the way interoperability supports health and care, this will be based around the clinical processes (ADPIE) and encounters (SOAP), this is a replacement to the existing approach based on exchanging data standards. This still supports delivering the data standard but we are breaking this down into components.

The high level view is:

- Encounters are recorded in EPR/EHR systems (out of scope for interoperability standards) and they are shared via **Shared Care Records**.
- Clinical Process is supported by  **Care Coordination** and so is focused on patient journeys and pathways. 

{{render:diagrams-CareProcess-technical-process}}

We will refer to both **Care Coordination** and **Shared Care Records** as *Frameworks*. 

Data Standards (e.g. UK Core) will be used by these frameworks (note: this excludes EHR/EPR data model standards).



