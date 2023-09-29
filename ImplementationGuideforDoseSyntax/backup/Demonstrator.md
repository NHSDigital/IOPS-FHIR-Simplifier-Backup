# Dosage Demonstrator (using FHIR STU3)

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    This page is in Experimental status. 
    <br/><br/>
    <strong>This demonstrator is currently aligned to FHIR STU3, not FHIR R4.</strong>
</div>

## Overview

A demonstrator, with associated API, has been developed by the North of England Commissioning Support Unit that uses this guidance.


<a href="https://dmdsite-uks-test-web.azurewebsites.net/" class="nhsd-a-button">
    Access to the demonstrator
</a>

<a href="https://apidmd001.azurewebsites.net/index.html" class="nhsd-a-button">
    Read the API documentation
</a>

The API is available to be used within prototype and alpha implementations. It is not recommended to be use for production implementations.

---

## Medication resource server prototype

An example of how a medication resource server may work to expose dm+d concepts as FHIR `Medication` resources. Switch to the 'developer view' to see the FHIR output as XML.

---

## Dose to text conversion demonstrator

Copy and paste any of the XML examples into the demonstrator and it will convert the complete instructions (`Medication` + `Dosage`) into a human readable string, following the algorithm described within this guidance.

---

## Dose to product translation demonstrator

Select any combination of VTM, dose quantity, route and form and the demonstrator will return an ordered list of equivilant VMPs following the algorithm described within this guidance.
