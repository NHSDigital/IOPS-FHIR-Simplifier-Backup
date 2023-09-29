---
topic: Introduction
---
## Introduction

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS Digital</div>
  
The National Pathology FHIR Messaging Specification supports the ability to share pathology results in NHS primary and secondary care settings. This release focuses on haematology and clinical biochemistry (also known as chemical pathology) test reporting. It defines a FHIR R4 payload derived from the UK Core to allow test results to be sent from a Laboratory Information Management System (LIMS) to a requesting system. It is anticipated that the messaging specification and implementation guidance will be updated following First of Type (FoT) implementation.

Potential future releases may include support for:

- Other pathology specialisms and diagnostic areas
- The definition of FHIR profiles to support pathology test requests


## Definition of Terms ##

When describing pathology reports different regions and professions sometimes use different words to describe the same entities. Therefore, for the avoidance of confusion, within the context of this guidance the following terms have these definitions:

- Test group – this describes any group of related tests that has been defined by the laboratory or other providing organisation. The individual tests within a test group may differ between organisations. Test groups are often referred to as batteries, panels and profiles. A common example is a Full Blood Count, with typically comprises approximately 16 individual tests.
- Test result - this is the result that has been provided by the laboratory or other provider. These may be standalone results or may be a part of a ‘Test group’. They are also sometimes referred to as test analytes.

