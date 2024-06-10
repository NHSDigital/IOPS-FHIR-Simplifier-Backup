
The items stated are the mandatory elements for the profile <code>{{variable:subject}}</code>. These are the differentials only, see the Profile  for more details

<fql>
from StructureDefinition
where url = %subject
for differential.element.where(min.exists())
select element:path, min, max
</fql>

