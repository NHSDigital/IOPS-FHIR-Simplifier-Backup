## `reasonReference`

An optional reference to a FHIR `Condition` or `Observation` resource.

If the clinical system has recorded the reason for medication (often known as the *indication*) as either a `Condition` or `Observation` resource then a logical link to that resource has business benefit.

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4> Recommendation:</h4>
If used, <code>reasonCode</code> and <code>reasonReference</code> are mutually exclusive and should not both be populated.
</div>

---
