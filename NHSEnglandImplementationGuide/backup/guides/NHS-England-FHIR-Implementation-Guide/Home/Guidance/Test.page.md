## FQL Testing

@```
using 'NHS England Programme Implementation Guides'
from Bundle
select *
```


# Constraints
@```
from StructureDefinition
where type = 'MedicationDispense'
for differential.element
select
id, join constraint { key, severity, human, expression }
```

# Bindings
@```
from StructureDefinition
where type = 'MedicationDispense'
for differential.element
select
id, join binding { strength, valueSet: '{{pagelink:ValueSet-' & valueSet.substring(29) & '}}' }
```

# Extensions
@```
from StructureDefinition
where type = 'MedicationDispense'
for differential.element where differential.element.path.contains('extension:')
select
sliceName, context: path.contains('extension:').replace('.extension', ''), join type { link: '{{pagelink:' & profile.substring(40) & '}}' }
```




# Examples:

## New Simplifier Template but only work well for Examples for now. Does not currently work with FQL
## Details in IOPS-2089 
<br>

{{page:Home/Examples/AllExamples/Example-England-HealthcareService-CancerScreeningCentre.page.md}}