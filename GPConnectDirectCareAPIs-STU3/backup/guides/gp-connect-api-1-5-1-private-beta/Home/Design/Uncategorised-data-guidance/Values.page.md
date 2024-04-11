## {{page-title}}

Values are any reading or result that is recorded with the uncategorised data. For example, the uncategorised data [50373000 | Body height measure (observable entity) |
](https://termbrowser.nhs.uk/?perspective=full&conceptId1=50373000) may have a value of 156cm.


### Individual values

The majority of uncategorised data that contains values will only have a single value. In these cases, the value will be exported in the `Observation.value[x]` element.

```xml
<Observation>
    ...
    <valueQuantity>
        <coding>
            <value value="156" />
            <unit value="centimeter" />
            <system value="http://unitsofmeasure.org" />
            <code value="cm" />
        </coding>
    </valueCodeableConcept>
    ...
</Observation>
```

### Multiple values

There are cases where an item of uncategorised data may contain multiple values. This happens when:

- there is a single clinical code that describes the uncategorised data as a whole and
- each recorded value in the uncategorised data is described by its own clinical code

In these cases, each value will be exported in an instance of `observation.component`.

This approach **MUST** be used for blood pressure readings where the systolic and diastolic values were taken together.

---