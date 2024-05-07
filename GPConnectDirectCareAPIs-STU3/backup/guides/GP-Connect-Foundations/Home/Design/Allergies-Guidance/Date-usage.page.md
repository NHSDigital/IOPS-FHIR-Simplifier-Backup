## {{page-title}}

The <code class="highlighter-rouge">AllergyIntolerance</code> resource supports a rich set of date concepts. However, there is currently limited support for additional date concepts via the allergy record structures in producing systems.

The asserted date is when the allergy related to the patient was asserted. In many cases, this will be when the allergy is entered on to the system, although systems may allow this date to be modified by the user.

If a producing system, currently or at a future point supports allergy date concepts that explicitly capture onset dates and last occurrence dates, then the <code class="highlighter-rouge">onsetDateTime</code> and <code class="highlighter-rouge">lastOccurrence</code> elements of <code class="highlighter-rouge">AllergyIntolerance</code> may be populated.