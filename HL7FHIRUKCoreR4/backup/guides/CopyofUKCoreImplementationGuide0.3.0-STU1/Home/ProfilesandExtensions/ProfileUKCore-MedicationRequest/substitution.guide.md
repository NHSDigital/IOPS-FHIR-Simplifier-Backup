## `substitution`


<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4>Important Note:</h4>
Within UK healthcare, substitution is not the norm so the international FHIR definition where "_If nothing is specified substitution may be done._" does not align with UK healthcare prescribing best practice.<br/>

It could be unwise to assume all UK implementations will prevent substitution if not explicitly stated, especially if the same clinical system has been previously implemented outside the UK. <br/>

UK Core has profiled this element as MANDATORY and MUST have a default boolean value of <code>false</code> to denote substitution is not allowed.

</div>

### Allowing substitution

Where substitution to be be allowed, set to `true`. The inclusion of the coded reason is optional as the valueset defined in FHIR is of limited benefit to UK healthcare.

---