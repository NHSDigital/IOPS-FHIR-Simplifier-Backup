## `substitution`

<b>Definition</b><br>

Within UK healthcare, substitution is not the norm and so this element will normally be set to a default of `false`.

Substitution being set to false is a mandatory requirement for EPS.

Substituition is a mandatory requirement for EPS

- Important Note: 

Within NHS healthcare, substitution is not the norm so the international FHIR definition where ;_If nothing is specified substitution may be done._" does not align with NHS healthcare prescribing best practice.
It could be unwise to assume all NHS implementations will prevent substitution if not explicitly stated, especially if the same clinical system has been previously implemented outside the NHS.

NHSE has profiled this element as MANDATORY and MUST have a default boolean value of `false` to denote substitution is not allowed 

**Allowing substitution**

Where substitution to be be allowed, set to true.The inclusion of the coded reason is optional as the valueset defined in FHIR is of limited benefit to NHS healthcare.