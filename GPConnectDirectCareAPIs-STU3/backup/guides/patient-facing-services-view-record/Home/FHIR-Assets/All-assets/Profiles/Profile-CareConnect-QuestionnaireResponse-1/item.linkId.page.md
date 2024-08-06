## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

Pointer to a specific item from a linked `Questionnaire`. Where the `QuestionnaireResponse` does not link back to a `Questionnaire` this should be populated with the rubric of the 'parent' observation. If the 'parent' observation does not have a text description which can be used, then populate with 'No information available'.

<h5><ins>Example</ins></h5>

```xml
<item>
    <linkId value="Body weight" />
</item>
```

---