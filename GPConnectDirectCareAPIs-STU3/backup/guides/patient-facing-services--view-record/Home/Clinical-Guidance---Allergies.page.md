## {{page-title}}

<h5><ins>category</ins></h5>

Code - Use medication for all drug allergy types, environment for all non-drug allergies.

<span class="mro-circle required" title="Required"></span> Recommended

<h5><ins>Patient Facing - View Record guidance</ins></h5>

It is advised to display `category` if it's in the clinical record. It is less significant from a Patient Facing Service (PFS) angle than clinician facing services. If a patient has an Allergy and can see ‘no known allergies’ are being displayed, then this should be displayed. Recording allergies is a point in time assessment. It’s possible to have no known Allergy and then some Allergy recorded. (A scenario may arise where an Allergy has been recorded and then a value of no-known Allergy is recorded.)

All Allergy information will be displayed together, whether this is part of Allergy profile or Observation. 

Should I separate medication (drug) and environmental allergies? - 
As with all design choices, this should be a decision for your clinician users and based around your clinical use case. Some use cases may see potential benefit in focussing more on one category of allergy / adverse reaction or the other or simply to display them in separate groups. In considering this, you should be aware of the way the category definition for use in DCAPI. If the allergy is not explicitly given a category of medication or environmental in the recording system, then it MUST be assigned a category of medication if the allergy/intolerance entry interacts with prescribing decision support in the source system. Otherwise, the category of environment will be used. There are circumstances where a non-drug allergy is given a medication category and where an adverse reaction to a drug may be given an environmental category.

Should the consuming system utilise the categorisation, then it must consider how it handles such data permutations. You may choose not to make use of the category and just present the detail of the allergy or intolerance.

DCAPI data examples
* Drug allergy as a product - Faverin 50mg tablets (Mylan)
* Drug allergy as disorder - Adverse reaction to erythromycin
* Drug allergy as finding - Penicillin allergy
* Degraded drug allergy - Sensitivity to Multilex action group: Antibacterials (in eye preparations)

<h5><ins>Further information</ins></h5>

In the profile, there are four values of AllergyIntoleranceCategory. Direct Care API (DCAPI), ask for only medication and environment to be used. 

1. food - Any substance consumed to provide nutritional support for the body (food is not readily classified). **NOT used within in DCAPI**
2. medication - Substances administered to achieve a physiological effect.
3. environment - Any substances that are encountered in the environment, including any substance not already classified as food, medication, or biologic.
4. biologic - A preparation that is synthesized from living organisms or their products, especially a human or animal protein, such as a hormone or antitoxin, that is used as a diagnostic, preventive, or therapeutic agent. Examples of biologic medications include: vaccines; allergenic extracts, which are used for both diagnosis and treatment (for example, allergy shots); gene therapies; cellular therapies. There are other biologic products, such as tissues, that are not typically associated with allergies. **NOT used within in DCAPI**

Note - Values of food or biologic fall under medication or environment.
