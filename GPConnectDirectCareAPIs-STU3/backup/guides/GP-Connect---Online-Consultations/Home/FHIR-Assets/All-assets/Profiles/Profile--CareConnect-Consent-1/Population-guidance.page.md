## {{page-title}}

- the `status` element **MUST** contain a fixed value of either `proposed`, `active`, or `rejected`
- the `category` element **SHOULD** contain a classification of the type of consent found in the statement
- the `patient` element **MUST** contain a reference to the patient the consent applies to
- the `period` element **SHOULD** contain the period this consent applies to
- the `consentingParty` element **SHOULD** contain a reference to who is agreeing to the policy and exceptions
- the `action` element **SHOULD** contain any actions controlled by this consent
- the `source[x]` element **SHOULD** reference the source from which the consent was taken
- the `policy` element **SHOULD** contain any policies covered by this consent
- the `purpose` element **SHOULD** contain the context of activities for which the agreement is made
- the `datePeriod` element **SHOULD** contain timeframe for data controlled by this consent
- the `data` element **SHOULD** contain the data controlled by this consent
- the `except` element **SHOULD** contain any exceptions to the base policy of this consent. An exception can be an addition or removal of access permissions