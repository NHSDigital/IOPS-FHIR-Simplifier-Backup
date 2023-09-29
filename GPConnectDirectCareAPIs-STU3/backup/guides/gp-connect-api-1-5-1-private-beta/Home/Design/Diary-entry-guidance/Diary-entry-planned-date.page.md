## {{page-title}}

<p>The planned date may be a single date or a date range according to the source GP clinical system and local recording practice. 
The GP clinical system provider is to determine whether its data supports the inclusion of a period for the planned date or can only meaningfully return a single planned date.
Wherever feasible and meaningful, a date period is preferred.
The planned date(s) may represent an earliest date, latest date, indicative date or a combination but this may vary by record / use and the resource will not provide distinctions in this respect.</p>

<p>Consumers may include a part parameter to return only diary entries up to a selected date in the future.
As the search filter only provides an upper boundary and has to be a future date, diary entries which are <code class="highlighter-rouge">active</code> and have passed their planned date will always be included.
Full details about search criteria for diary entries is detailed in the 

[Search criteria](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_search.html#diary-entries)

and [Retrieve a patient’s structured record](https://developer.nhs.uk/apis/gpconnect-1-6-0/accessrecord_structured_development_retrieve_patient_record.html#request-operation) pages.
