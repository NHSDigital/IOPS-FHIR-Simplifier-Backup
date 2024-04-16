## {{page-title}}

Provider systems **SHOULD** provide a consistent order to elements within the `Bundle` resource. It is recommended to follow the order described in the bundle population illustrated diagram below.

{{ render:structured-bundle-response.png }}

<br>

Consumer systems **MUST NOT** rely on order or index of elements within the `Bundle` resource in order to parse encapsulated resources.