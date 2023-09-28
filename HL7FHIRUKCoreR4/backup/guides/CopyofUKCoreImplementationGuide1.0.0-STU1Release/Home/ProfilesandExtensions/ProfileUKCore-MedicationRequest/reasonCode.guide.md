## `reasonCode`

Optional.

Useful to the wider clinical team as an additional safety check, especially if the requested medication is normally prescribed for different reasons, to avoid confusion between clinical teams. Recording an indication against a medication request also gives valuable insight when data is collated for secondary uses, especially if linked with outcome data.

Where possible this should be a coded term from the SNOMED-CT hierarchy as a descendant of the concept [404684003 (Clinical finding)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=404684003&edition=uk-edition); however, free-text reasons are also acceptable.


<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4> Recommendation:</h4>
If used, <code>reasonCode</code> and <code>reasonReference</code> are mutually exclusive and should not both be populated.
</div>

---
