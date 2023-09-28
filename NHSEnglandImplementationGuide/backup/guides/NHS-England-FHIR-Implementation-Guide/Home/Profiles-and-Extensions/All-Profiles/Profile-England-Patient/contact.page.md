## `contact`

<b>Definition:</b>

A list of patient contacts. Only emergency contacts are returned and only emergency contacts should be added. Any other contacts should be added to the patients Related Person. Patients designate here any contact number they desire to be used in case of an emergency. Note, while a patient may also desire to record various related persons telecom details, these do not separately allow for a concept of emergency contact; only ranking. See RelatedPerson endpoint. When a patient tagged as restricted or very restricted is retrieved, all contacts are removed from the response.

---