## {{page-title}}

Depending on the GP Connect version supported by the provider system it can be possible for the consultation to link to a clinical item that the provider system is not yet able to export with GP Connect. For example, if the consultation contains a link to a referral record, but the provider system does not yet support exporting referrals.

Where a provider system is not able to export a linked clinical item, it will create a `section.section.entry` (or `section.entry`) entry with the:

- `List.entry.item.display` with the value of "[Clinical area] items are not supported by the provider system."

        Where [Clinical area] identifies the type of the clinical item that is not supported.

The example below shows references to two items, one for an observation, and the other for referrals that aren't supported by the provider system.

```xml
<List>
    ...
    <section>
        <entry>
            <item>
                <reference value="observation-99asd2" />
            </item>
            <item>
                <display value="Referral items are not supported by the provider system" />
            </item>
        </entry>
    </section>
</List>
```

```json
{
  "item": {
    "reference": "Observation/6734572634"
  }
},
{
  "item": {
    "display": "Referral items are not supported by the provider system"
  }
}
```

---