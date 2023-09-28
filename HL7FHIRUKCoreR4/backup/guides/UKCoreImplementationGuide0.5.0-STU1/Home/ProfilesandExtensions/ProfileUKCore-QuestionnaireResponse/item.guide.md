## <code>{{page-title}}</code>

A group or question item from the original questionnaire for which answers are provided.


`item.linkId`

The item from the Questionnaire that corresponds to this item in the QuestionnaireResponse resource.


`item.definition`

A reference to an ElementDefinition that provides the details for the item.


`item.text`

Text that is displayed above the contents of the group or as the text of the question being answered.


`item.answer`

The respondent's answer(s) to the question.

- `item.answer.value[x]`	Optional answer (or one of the answers) provided by the respondent to the question.
- `item.answer.item`	Optional nested groups and/or questions found within this particular answer.


`item.item`

Text, questions and other groups to be nested beneath a question or group.

---
