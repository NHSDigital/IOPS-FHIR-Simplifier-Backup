## <code>{{page-title}}</code>

A particular question, question grouping or display text that is part of the questionnaire.


`item.linkId`

An identifier that is unique within the Questionnaire allowing linkage to the equivalent item in a QuestionnaireResponse resource.


`item.definition`

This element is a URI that refers to an ElementDefinition that provides information about this item, including information that might otherwise be included in the instance of the Questionnaire resource.


`item.code`

A terminology code that corresponds to this group or question.

This element currently uses a FHIR example <a href="https://simplifier.net/packages/hl7.fhir.r4.core/4.0.1/files/82547">Questionnaire Question Codes ValueSet</a> consisting of any concept from LOINC.


`item.prefix`

A short label for a particular group, question or set of display text within the questionnaire used for reference by the individual completing the questionnaire.


`item.text`

The name of a section, the text of a question or text content for a display item.


`item.type`

The type of questionnaire item this is - whether text for display, a grouping of other items or a particular type of data to be captured (string, integer, coded choice, etc.).

Defines the format in which the user is to be prompted for the answer.

Additional constraints on the type of answer can be conveyed by extensions. The value may come from the ElementDefinition referred to by .definition.

This element **MUST** be present for an item and use a value from the CodeSystem below:

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render:http://hl7.org/fhir/item-type}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://hl7.org/fhir/item-type}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://hl7.org/fhir/item-type}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://hl7.org/fhir/item-type}}
</div>

<br/>

`item.enableWhen`

A constraint indicating that this item should only be enabled (displayed/allow answers to be captured) when the specified condition is true.

This element is labelled as a modifier because if enableWhen is present and the condition evaluates to false, then the Questionnaire behaves as though the elements weren't actually present.

- `item.enableWhen.question`	The linkId for the question whose answer (or lack of answer) governs whether this item is enabled.
- `item.enableWhen.operator`	Specifies the criteria by which the question is enabled.
- `item.enableWhen.answer[x]`	A value that the referenced question is tested using the specified operator in order for the item to be enabled.


`item.enableBehavior`

Controls how multiple enableWhen values are interpreted - whether all or any must be true.

This element may optionally be present and **MUST** use a value from the CodeSystem below:

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'HTML View')">HTML View</button>
 <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
  <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="HTML View" class="tabcontent" style="display:block">
  <h3>HTML View</h3>
{{render:http://hl7.org/fhir/questionnaire-enable-behavior}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://hl7.org/fhir/questionnaire-enable-behavior}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://hl7.org/fhir/questionnaire-enable-behavior}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://hl7.org/fhir/questionnaire-enable-behavior}}
</div>

<br/>

`item.required`

An indication, if true, that the item must be present in a "completed" QuestionnaireResponse.


`item.repeats`

An indication, if true, that the item may occur multiple times in the response.


`item.readOnly`

An indication, when true, that the value cannot be changed by a human respondent to the Questionnaire.


`item.maxLength`

The maximum number of characters that are permitted in the answer to be considered a "valid" QuestionnaireResponse.


`item.answerValueSet`

A reference to a value set containing a list of codes representing permitted answers for a "choice" or "open-choice" question.


`item.answerOption`

One of the permitted answers for a "choice" or "open-choice" question.

- `item.answerOption.value[x]`	Mandatory potential answer that's allowed as the answer to this question.
- `item.answerOption.initialSelected`	Optionally indicates whether the answer value is selected when the list of possible answers is initially shown.


`item.initial`

One or more values that should be pre-populated in the answer when initially rendering the questionnaire for user input.


`item.item`

Text, questions and other groups to be nested beneath a question or group.

---
