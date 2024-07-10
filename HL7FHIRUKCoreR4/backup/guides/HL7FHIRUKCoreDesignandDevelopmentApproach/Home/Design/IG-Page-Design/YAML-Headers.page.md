## {{page-title}}

A UK Core profile index page should have four YAML headers:
- a `topic`, which allows the page to be referenced using \{ \{pagelink:[topic]\}\} within the IG. 
- a `system`, the canonical url for the resource, which allows Simplifier render commands to be used without specifying a url 
- a `usage`, the canonical url for the base resource, which allows Simplifier fql commands to determine refrerences to this profile
- a `issue`, the id for the resource, which allows Simplifier FQL and variables to display

A YAML header SHALL be the first item on a page, it SHALL be unique, and it SHALL be in the following format: 

~~~html
---
topic: [Section]-[ResourceName]
subject: [resource url]
usage: [base url]
issue: [resource id]
---
~~~

Example Topics:
- Guidance-DataType
- Library-Extensions
- Profile-MedicationDispense
- Home-ContactUs

**Note**: The topic only needs to be added for pages that will be linked to directly, and for pages with non unique names, such as <code>Index</code> - for uniquely named pages e.g. <code>ValueSet UKCore-[ValuesetName]</code>, the default generated topic is ok. 

---