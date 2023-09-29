## Element: `basedOn` <span class="mro-circle optional" title="Optional"></span>

A reference to any number of `CarePlan`, `MedicationRequest`, `ServiceRequest` or `ReferralRequest` resources.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
   <strong>Recommendation</strong>: not implemented as part of an MVP to reference a previous medication request. Instead use <code>priorPrescription</code>.
   <br />
   <br />
   If the clinical system has implemented the <code>CarePlan</code> resource, a logical link to the care plan for which the medication request is based has business benefit.
</div>


---