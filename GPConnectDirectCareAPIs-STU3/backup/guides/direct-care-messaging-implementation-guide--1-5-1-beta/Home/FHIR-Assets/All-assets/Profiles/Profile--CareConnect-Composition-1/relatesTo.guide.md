## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

See {{pagelink:Home/Build/How-to-handle-updates-to-documents}} for more information.

- the `relatesTo.code` element **MUST** contain the fixed value of `replaces`

- the `relatesTo.targetIdentifier` element **MUST** contain the UUID of the previous message if an updated or replacement document is being sent




<h5><ins>Example</ins></h5>

```xml
<relatesTo>
    <code value="replaces" />
    <targetIdentifier value="e255cf10-db3c-11ec-9d64-0242ac120002" />
</relatesTo>
```

---