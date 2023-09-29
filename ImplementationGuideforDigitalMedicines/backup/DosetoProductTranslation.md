# {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    This page is in Experimental status.
</div>

## Overview

This page describes an important functional requirement for many system implementations using Dose Syntax. Structured Dose Syntax information must be capable of being used to support dose-based and product-based prescribing, and there is a requirement to convert between the two - e.g. to convert a dose-based prescription to an actual product for dispensing within a pharmacy.

Details of the requirements for dosage format conversion are highly use-case dependent and will be addressed as work in specific use-case areas develops.

### Background

When a prescriber uses a dose-based instruction (using a VTM), it will always need to be translated into a product-based instruction (using a VMP or AMP) to be supplied or dispensed. Today, this is a highly manual process performed by a clincian. For example;

A hospital pharmacist would translate dose-based orders coming from the ward into a products that is both in-stock and suitable to meet the patients’ needs.

A GP would translate dose-based medication requests within a discharge letter into product-based repeat prescriptions.

---
