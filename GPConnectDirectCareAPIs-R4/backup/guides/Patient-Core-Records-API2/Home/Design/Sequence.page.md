## {{page-title}}

### 1. Provider update with notification

The sequence below highlights the flow of events in a scenario where an patient record has been updated and subscribers are notified of this update. They would then use the API to retrieve the data from the provider.

{{render:pcrapi1-sequence.png}}



### 2. Send update to record to a central service

This sequence will be followed when an update is to be sent to a central repository (and/or) another system. 

{{render:sys-post-central-sequence.png}}


### 3. Retrieve data from the central repository




