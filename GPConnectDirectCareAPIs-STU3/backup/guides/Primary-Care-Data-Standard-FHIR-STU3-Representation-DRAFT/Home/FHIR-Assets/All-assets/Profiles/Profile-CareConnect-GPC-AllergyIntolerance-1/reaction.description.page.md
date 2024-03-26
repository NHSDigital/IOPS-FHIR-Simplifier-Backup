## {{page-title}}


<h5><ins>Usage</ins></h5>

<span class="mro-circle optional" title="Optional"></span> Optional


<h5><ins>Guidance</ins></h5>

Conveys the textual description of the manifestation where no code is available.

A consuming system **MAY** concatenate the contents (appropriately labelled) with text in `AllergyIntolerance.note` if a textual description of the manifestation is not supported in the receiving system record structure.

<h5><ins>Example</ins></h5>

```xml
<reaction>
    <description value="Vivamus rhoncus mi id urna mattis, a fringilla quam congue." />
</reaction>
```

---