## {{page-title}}

GP Connect's vision is to accelerate and extend data access to patients in an efficient way. Part of this acceleration is patient-facing services (PFS), which enable seamless access of data for patients from Foundation System suppliers.

This implementation guide focuses on the Prescriptions Management API, developed to allow patients to view their current prescriptions, request a new instance of their current prescriptions and cancel a prescription request.

API Management (APIM) policy requires that any new APIs conform to FHIR R4 UKCore standard. 

## Purpose of the API ##

GP Connect is developing a new set of patient-facing services APIs to standardise the PFS APIs for new market entrants (NMEs) and foundation system suppliers.  This work will support a new foundation supplier’s integration with the NHS app. This Alpha project outlines the proposed solution design for Prescription Management APIs required.

## Problem statement ##

Ideally the prescriptions management API will include considerations for all functionality required for management of prescriptions and pharmacy nominations. Currently we are working towards a minimum viable product (MVP) specification for the API to advance the onboarding of additional foundation suppliers onto the standardised API structure. This means that further work will be required in the future to expand the functionality of the API to include those items listed as out of scope. The limited nature of the MVP API means that current foundation suppliers will be reluctant to make use of the standardised API until it includes additional functionality which they offer as part of their bespoke solutions already in place. We seek to reduce this by completing a gap analysis between the current requirements for the MVP and foundation supplier API specifications, making future functionality suggestions where appropriate, and with direct cooperation between the design team and foundation suppliers where possible.

