## {{page-title}}

Important note regarding the use of the "preferred" binding strength for UK Core ValueSets containing CodeSystems specific to individual UK countries.
Where different countries within the UK use different sets of concepts for the same data item, currently the default approach to supporting this data within the UK Core is to create a CodeSystem for each individual country where requirements have been confirmed, and incorporate each such CodeSystem within a ValueSet that is then bound into the profile or extension supporting the data item (referred to as the "individual country specific CodeSystem" approach).

In most cases where this approach is taken, for some of the concepts the ValueSet does contain more than one entry for the same concept. For this reason, the use of the "extensible" binding strength is deemed to be inappropriate and "preferred" is determined to be the most suitable binding strength to use instead.

---

