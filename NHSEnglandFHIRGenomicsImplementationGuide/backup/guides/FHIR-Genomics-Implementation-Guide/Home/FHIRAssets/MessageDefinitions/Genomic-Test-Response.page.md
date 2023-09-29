## {{page-title}}

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/genomic-test-response'
select Name: name, Url: url, Status: status, Date: date

```

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/genomic-test-response'
for focus
select Code: code, Profile: '<a href=https://simplifier.net/resolve?target=simplifier&scope=uk.nhsdigital.r4&canonical='+ profile + '>'+profile+'</a>', Min: min, Max: max

```

@```
from MessageDefinition
where url='https://fhir.nhs.uk/MessageDefinition/genomic-test-response'
for eventCoding
select System: system, Code: code

```

---