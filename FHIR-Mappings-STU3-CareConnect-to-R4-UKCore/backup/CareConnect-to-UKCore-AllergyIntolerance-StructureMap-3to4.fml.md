map "http://hl7.org/fhir/StructureMap/AllergyIntolerance3to4" = "Conversions for STU3 CareConnect and R4 UKCore AllergyIntolerance"

uses "http://hl7.org/fhir/3.0/StructureDefinition/AllergyIntolerance" alias AllergyIntoleranceR3 as source
uses "http://hl7.org/fhir/4.0/StructureDefinition/AllergyIntolerance" alias AllergyIntolerance as target

imports "http://hl7.org/fhir/StructureMap/*3to4"

group AllergyIntolerance(source src : AllergyIntoleranceR3, target tgt : AllergyIntolerance) extends DomainResource <<type+>> {
  src.extension as ext where $this.url='https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-AllergyIntoleranceEnd-1'
    -> tgt.extension = create('Extension') as tgtext, tgtext.url = 'https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-AllergyIntoleranceEnd' then {
      ext.extension as vs -> tgtext as vt, vt.extension = vs; 
  };
  src.extension as ext where $this.url='http://hl7.org/fhir/StructureDefinition/encounter-associatedEncounter'
    -> tgt.encounter as vt then {
      ext.value: Reference as vs -> vt as vt1, tgt.encounter = vs;
  };
  src.extension as ext where $this.url='https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-Evidence-1'
    -> tgt.extension = create('Extension') as tgtext, tgtext.url = 'https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-Evidence' then {
      ext.value: Reference as vs -> tgtext.value = create('Reference') as vt, tgtext.value = vs;
  };

  src.identifier -> tgt.identifier;
  src.clinicalStatus as vs ->  tgt.clinicalStatus as vt,  vt.coding as c,  c.system = 'http://terminology.hl7.org/CodeSystem/allergyintolerance-clinical',  c.code = vs;
  src.verificationStatus as vs ->  tgt.verificationStatus as vt,  vt.coding as c,  c.system = 'http://terminology.hl7.org/CodeSystem/allergyintolerance-verification',  c.code = vs;
  src.type -> tgt.type;
  src.category -> tgt.category;
  src.criticality -> tgt.criticality;

  src.code : CodeableConcept as vs -> tgt.code = create('CodeableConcept') as vt then CodeableConceptAllergyIntolerance(vs, vt);

  src.patient -> tgt.patient;
  src.onset : dateTime as vs -> tgt.onset = create('dateTime') as vt then dateTime(vs, vt);
  src.onset : Age as vs -> tgt.onset = create('Age') as vt then Age(vs, vt);
  src.onset : Period as vs -> tgt.onset = create('Period') as vt then Period(vs, vt);
  src.onset : Range as vs -> tgt.onset = create('Range') as vt then Range(vs, vt);
  src.onset : string as vs -> tgt.onset = create('string') as vt then string(vs, vt);
  src.assertedDate -> tgt.recordedDate "recordedDate";
  src.recorder -> tgt.recorder;
  src.asserter -> tgt.asserter;
  src.lastOccurrence -> tgt.lastOccurrence;
  src.note -> tgt.note;
  src.reaction as vs0 -> tgt.reaction as vt0 then {
    vs0.substance : CodeableConcept as vs1 -> vt0.substance = create('CodeableConcept') as vt1 then CodeableConceptAllergyIntolerance(vs1, vt1);
    vs0.manifestation : CodeableConcept as vs1 -> vt0.manifestation = create('CodeableConcept') as vt1 then CodeableConceptAllergyIntolerance(vs1, vt1);
    vs0.description -> vt0.description;
    vs0.onset -> vt0.onset;
    vs0.severity -> vt0.severity;
    vs0.exposureRoute : CodeableConcept as vs1 -> vt0.exposureRoute = create('CodeableConcept') as vt1 then CodeableConceptAllergyIntolerance(vs1, vt1);
    vs0.note -> vt0.note;
  };
}

group CodeableConceptAllergyIntolerance(source src : CodeableConcept, target tgt : CodeableConcept) {
  src.coding as vs -> tgt.coding = create('Coding') as vt then SctCoding(vs, vt);
  src.text as text -> tgt.text = text;
}

group SctCoding(source src : Coding, target tgt : Coding) {
  src.system as system -> tgt.system = system;
  src.version as version -> tgt.version = version;
  src.code as code -> tgt.code = code;
  src.display as display -> tgt.display = display;
  src.userSelected as userSelected -> tgt.userSelected = userSelected;

  src.extension as vs where $this.url='https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid' or 
                            $this.url='https://fhir.nhs.uk/STU3/StructureDefinition/Extension-coding-sctdescid' ->
    tgt.extension = create('Extension') as vt, vt.url = 'https://fhir.hl7.org.uk/StructureDefinition/Extension-UKCore-CodingSCTDescId' then {

      vs.extension as vsx where $this.url='descriptionId' -> vt.extension = create('Extension') as vtx, vtx.url = 'descriptionId' then {
        vsx.value: id as vsv -> vtx.value = create('Identifier') as vtv, 
          vtv.system='http://snomed.info/sct',
          vtv.value = vsv;
      };

      vs.extension as vsx where $this.url='descriptionDisplay' -> vt.extension = create('Extension') as vtx, vt.extension = vsx;
    };
}
