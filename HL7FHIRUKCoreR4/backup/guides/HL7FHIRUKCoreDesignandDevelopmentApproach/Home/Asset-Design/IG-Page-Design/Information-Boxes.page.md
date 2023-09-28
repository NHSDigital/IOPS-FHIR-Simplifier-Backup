## Information Boxes 

There are two information boxes in use in the IG, a blue box and a yellow box. 

Blue should be used for additional callouts of information, e.g.:
~~~~html
<div markdown="span" class="alert alert-info"><i class="fa fa-asterisk"></i> <code>UKCore-MedicationAdministrationCategory</code> was added after specific review and feedback from the Digital and Interoperable Medicines Programme. It was not added under a Clinical & Technical Assurance sprint
</div>
~~~~
<div markdown="span" class="alert alert-info"><i class="fa fa-asterisk"></i> <code>UKCore-MedicationAdministrationCategory</code> was added after specific review and feedback from the Digital and Interoperable Medicines Programme. It was not added under a Clinical & Technical Assurance sprint
</div>

Yellow should be used for important information, e.g.:
~~~~html
<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> Important</h4>
Where the prescription is available, it is recommended to reference via a URL - using the <code>MedicationDispense.authorizingPrescription.identifier</code> element rather than adding the <code>MedicationRequest</code> as a bundle - to avoid duplication.
</div>
~~~~
<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-info-circle"></i> Important</h4>
Where the prescription is available, it is recommended to reference via a URL - using the <code>MedicationDispense.authorizingPrescription.identifier</code> element rather than adding the <code>MedicationRequest</code> as a bundle - to avoid duplication.
</div>

---