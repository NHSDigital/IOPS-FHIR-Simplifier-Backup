## Element: `substitution` <span class="mro-circle mandatory" title="Mandatory"></span>

Within UK healthcare, substitution is not the norm so the international FHIR definition where "_If nothing is specified substitution may be done._" **does not align** with UK healthcare prescribing best practice.

It could be unwise to assume all UK implementations will prevent substitution if not explicitly stated, especially if the same clinical system has been previously implemented outside the UK. 

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
   It is therefore recommended that this element is <strong>business required</strong> with a default boolean value of <code>false</code> to denote substitution is <strong>not allowed</strong>.
</div>

### Allowing substitution

Where substitution to be be allowed, set to `true`. The inclusion of the coded reason is optional as the valueset defined in FHIR is of limited benefit to UK healthcare.

---