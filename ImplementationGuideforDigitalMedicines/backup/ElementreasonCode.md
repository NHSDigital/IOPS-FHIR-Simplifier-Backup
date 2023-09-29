## Element: `reasonCode` <span class="mro-circle optional" title="Optional"></span>

Optional, but useful to the wider clinical team as an additional safety check, especially if the requested medication is normally prescribed for different reasons, to avoid confusion between clinical teams. Recording an indication against a medication request also gives valuable insight when data is collated for secondary uses, especially if linked with outcome data.

Where possible this should be a coded term from the SNOMED-CT hierarchy as a descendant of the concept [404684003 (Clinical finding)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=404684003&edition=uk-edition); however, free-text reasons are also acceptable.

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Recommendation</strong>: if used <code>reasonCode</code> and <code>reasonReference</code> are mutually exclusive and not both populated.
</div>

---