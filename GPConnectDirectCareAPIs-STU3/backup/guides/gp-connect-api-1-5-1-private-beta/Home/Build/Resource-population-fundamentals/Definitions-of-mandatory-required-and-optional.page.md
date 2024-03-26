## {{page-title}}

Throughout the profile pages within the specification we have a label for each data item named "Optionality", which details whether or not it has to be included in the resource. This item has 3 possible values:

1. Mandatory - if the data item **MUST** be recorded in the resource every time it is produced.
2. Required - if the system that is providing the data item contains this piece of data then it **MUST** include it in the resource.
3. Optional - the system has the option to include this data if it is available.

An example of a 'required' data item is the extension to the MedicationRequest profile for StatusReason.

StatusReason is used in GP Connect to carry information about why the status of a medication has been changed to stopped. In GP systems when a medication is stopped the clinician has to enter a date when it was stopped and the reason why it was stopped.

Clearly not every medication will have a status of stopped but when it does this information is of a high clinical importance and **MUST** be included in the message.
