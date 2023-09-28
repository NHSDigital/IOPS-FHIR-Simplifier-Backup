## {{page-title}}

A UK Core profile index page should have two YAML headers:
- a `topic`, which allows the page to be referenced using \{ \{pagelink:[topic]\}\} within the IG. 
- a `system`, the canonical url for the resource, which allows Simplifier render commands to be used without specifying a url 



A YAML header SHALL be the first item on a page, it SHALL be unique, and it SHALL be in the following format: 

~~~html
---
topic: [Section]-[ResourceName]
subject: [resource canonical url]
---
~~~

Example Topics:
- Guidance-DataType
- Library-Extensions
- Profile-MedicationDispense
- Home-ContactUs

**Note**: The topic only needs to be added for pages that will be linked to directly, and for pages with non unique names, such as <code>Index</code> - for uniquely named pages e.g. <code>ValueSet UKCore-[ValuesetName]</code>, the default generated topic is ok. 

---