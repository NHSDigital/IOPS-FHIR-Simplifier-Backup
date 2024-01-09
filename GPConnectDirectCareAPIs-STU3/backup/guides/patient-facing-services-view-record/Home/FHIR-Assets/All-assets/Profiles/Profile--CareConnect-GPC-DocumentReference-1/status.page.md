## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

The status of the `DocumentReference`.

Valid values are:

- `current` - the current reference for this document
- `superseded` - this reference has been superseded by another referernce
- `entered-in-error` - reference created in error

However, this field will always have default value of `current` as only the latest version of the document is retrieved.

<h5><ins>Example</ins></h5>

```xml
<status value="current"/>
```

---