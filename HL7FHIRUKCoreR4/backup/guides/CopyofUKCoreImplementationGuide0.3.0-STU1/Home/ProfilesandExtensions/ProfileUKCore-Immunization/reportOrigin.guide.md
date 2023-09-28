## `reportOrgin`

The source of the data when the report of the immunization event is not based on information from the person who administered the vaccine.

Should not be populated if primarySource = `true`, not required even if primarySource = `false`.


XML
```xml
<reportOrigin>
    <text value="RR8 - LEEDS TEACHING HOSPITALS NHS TRUST"/>
</reportOrign>
```
JSON
```json
{
"reportOrigin": {
        "text": "RR8 - LEEDS TEACHING HOSPITALS NHS TRUST"
    },
}
```

---