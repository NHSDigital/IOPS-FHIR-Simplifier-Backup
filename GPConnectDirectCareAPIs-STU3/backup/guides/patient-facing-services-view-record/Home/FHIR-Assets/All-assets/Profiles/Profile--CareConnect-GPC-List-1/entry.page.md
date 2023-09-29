## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

Individual entries within the `List` resource.

The `entry.item` will contain a reference to a profile which represents a clinical record entry in the source system.

For example:

- medication
- allergy
- problem
- diagnosis
- and so on

They will be recorded in the same order that the items appear when viewed in a consultation in the GP system.

<h5><ins>Example</ins></h5>

```xml
<entry>
    <!-- Patient Medicine Change Types -->
    <flag>
        <coding>
            <system value="urn:oid:1.2.36.1.2001.1001.101.104.16592" />
            <code value="04" />
            <display value="Prescribed" />
        </coding>
    </flag>
    <deleted value="false" />
    <date value="2022-11-01T11:09:00Z" />
    <item>
        <reference value="medication-001123" />
    </item>
</entry>
```

---