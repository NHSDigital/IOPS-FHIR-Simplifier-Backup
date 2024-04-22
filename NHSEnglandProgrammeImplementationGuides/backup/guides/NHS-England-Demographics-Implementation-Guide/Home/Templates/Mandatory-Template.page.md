
## {{page-title}}

The items stated are the mandatory elements for the profile. These are the differentials only. See the Profile <code>{{variable:subject}}</code> for more details

<fql>
from StructureDefinition
where url = %subject
for differential.element.where(min.exists())
select element:path, min, max
</fql>

