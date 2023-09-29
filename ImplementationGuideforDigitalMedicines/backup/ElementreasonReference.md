## Element: `reasonReference` <span class="mro-circle optional" title="Optional"></span>

A reference to a FHIR `Condition` or `Observation` resource.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Recommendation</strong>: not used as part of an MVP. However if the clinical system has recorded the reason for medication (often known as the <code>indication</code>, as either a <code>Condition</code> or <code>Observation</code> resource) then a logical link to that resource has business benefit. If implemented, <code>reasonCode</code> and <code>reasonReference</code> are mutually exclusive and should not both be populated.
</div>

---