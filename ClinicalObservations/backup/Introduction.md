## Introduction

There are a number of Early Warning Scores used for different types of patients:

- National Early Warning Scores (**NEWS2**) for patients 16 years of age or older
- Paediatric Early Warning Scores (**PEWS**) for children or young people
- Neonatal Early Warning Trigger Scores (**NEWTS**)
- Maternity Early Obstetric Warning Score (**MEOWS**)

Of these standards only one, NEWS2, has been developed as a FHIR specification (STU3) by NHS Digital and clinically assured.

Going forward a generic FHIR R4 messaging specification will be developed that initially covers NEWS2 and subsequently PEWS but could be further enhanced to include NEWTS and MEOWS, subject to requirements and clinical ownership.

### Approach ###
The approach to this work is to create a generic set of profiles and associated FHIR assets to support all current clinical observations. This will provide the flexibility for any future requirements

### Delivery ###

The products will include in delivery order:
1.	Upversion NEWS2 from STU3 to FHIR R4
2.	Enhancing and extending NEWS2 to rectify known issues in FHIR STU3, raised by vendors and users. 



### How NEWS2 Works ###

Reproduced from: Royal College of Physicians. National Early Warning Score (NEWS) 2: Standardising the assessment of acute-illness severity in the NHS. Updated report of a working party. London: RCP, 2017.

The NEWS2 is based on a simple aggregate scoring system in which a score is allocated to physiological measurements, already recorded in routine practice, when patients present to, or are being monitored in hospital. Six simple physiological parameters plus an inspired oxygen observation form the basis of the scoring system:

1. Respiration rate
2. Oxygen saturation
3. Systolic blood pressure
4. Pulse rate
5. Level of consciousness or new confusion*
6. Temperature.
7. Inspired oxygen

*The patient has new-onset confusion, disorientation and/or agitation, where previously their mental state was normal – this may be subtle. The patient may respond to questions coherently, but there is some confusion, disorientation and/or agitation. This would score 3 or 4 on the GCS (rather than the normal 5 for verbal response), and scores 3 on the NEWS2 system.

A score is allocated to each parameter as they are measured, with the magnitude of the score reflecting how extremely the parameter varies from the norm. The score is then aggregated and uplifted by 2 points for people requiring supplemental oxygen to maintain their recommended oxygen saturation.

This is a pragmatic approach, with a key emphasis on system-wide standardisation and the use of physiological parameters that are already routinely measured in NHS hospitals and in pre-hospital care, recorded on a standardised clinical chart – the NEWS2 chart.

A full [description of NEWS2](https://www.rcplondon.ac.uk/projects/outputs/national-early-warning-score-news-2) is available from the Royal College of Physicians.

{{render:NEWS2Chart}}

### How PEWS Works ###

PEWS has 4 charts depending on the age of the child

- NATIONAL PEWS chart 0-1yrs
- NATIONAL PEWS chart 1-5yrs
- NATIONAL PEWS chart 5-12yrs
- NATIONAL PEWS chart >12yrs

A full [description of PEWS](https://www.rcn.org.uk/clinical-topics/children-and-young-people/development-of-a-paediatric-early-warning-scoring-system) is available from the Royal College of Nursing.
