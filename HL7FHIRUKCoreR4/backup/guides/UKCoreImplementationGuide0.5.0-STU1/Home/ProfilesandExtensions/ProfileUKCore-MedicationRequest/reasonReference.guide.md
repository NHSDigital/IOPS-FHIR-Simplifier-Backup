## `reasonReference`

An optional reference to Condition or Observation that supports why the prescription is being written by reference. The resource being referenced should conform to one of the following:

- {{pagelink:Profile-Condition-9b7ea445-dc59-42d4-82e3-e48615907563}}
- <a href="https://simplifier.net/hl7fhirukcorer4/ukcoreobservation">UKCore-Observation Profile.</a>


If the clinical system has recorded the reason for medication (often known as the *indication*) as either a `Condition` or `Observation` resource then a logical link to that resource has business benefit.

Condition or observation that supports why the prescription is being written

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4> Recommendation:</h4>
If used, <code>reasonCode</code> and <code>reasonReference</code> are mutually exclusive and should not both be populated.
</div>

---
