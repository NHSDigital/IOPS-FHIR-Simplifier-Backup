## Element: `{{page-title}}`

The binding strength for site is preferred, meaning SNOMED codes from any hierarchy are allowed. The preferred binding defined within the UKCore standard is descendants of the concept [442083009 Anatomical or acquired body structure (body structure](https://termbrowser.nhs.uk/?perspective=full&conceptId1=442083009&edition=uk-edition).

We recommend descendants from the concept [278001007 Nonspecific site (body structure)](https://termbrowser.nhs.uk/?perspective=full&conceptId1=278001007&edition=uk-edition) are also supported within an implementation.

```xml
<!-- Site -->
<site>
    <coding>
        <system value="http://snomed.info/sct"/>
        <code value="59380008"/>
        <display value="Anterior abdominal wall structure"/>
    </coding>
</site>
```

---