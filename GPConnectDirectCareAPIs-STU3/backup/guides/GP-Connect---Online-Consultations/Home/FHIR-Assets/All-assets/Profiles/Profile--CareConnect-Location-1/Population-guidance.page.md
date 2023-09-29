## {{page-title}}

- the `identifier` element **MUST** contain a site ODS code to identify the organization at site level
- the `status` element **MUST** contain a fixed value of `active`
- the `name` element **MUST** contain the name of the location used by humans
- the `type` element **SHOULD** contain the type of function being performed at this location
- the `telecom` element **MUST** contain the telephone number of that location - that is, where `telecom.system` is set to a fixed value of `phone`, and `telecom.value` contains the `telephone number`
- the `address` element **SHOULD** contain the physical address of the location