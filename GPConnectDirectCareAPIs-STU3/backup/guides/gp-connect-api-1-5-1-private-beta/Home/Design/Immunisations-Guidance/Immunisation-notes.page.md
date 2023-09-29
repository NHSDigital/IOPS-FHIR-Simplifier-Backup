## {{page-title}}

GP systems that support a note entry against the immunisation <strong>MUST</strong> populate the text to the <code>note</code> element.
Additionally, any other information relevant to the immunisation which does not have a suitable, supported element within the <code class="highlighter-rouge">Immunization</code> resource <strong>MUST</strong> be populated to the <code>note</code> as a key value pair.
This includes where there is an element in the profile for the type of information, but the data type is not compatible with the way the data is recorded in the GP system.
For example, if the GP system holds the dosage information in a format which does not comply with the <code>doseQuantity</code> element’s <code>Quantity</code> datatype, then it may be returned as a note key value pair.