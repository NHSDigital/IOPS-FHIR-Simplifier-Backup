## {{page-title}}

The following triple will be used to represent an average reading from an ambulatory blood pressure monitoring (ABPM) device.


- **Header**: [2181371000000107 |Average ambulatory blood pressure (observable entity)|](https://termbrowser.nhs.uk/?perspective=full&conceptId1=2181371000000107)
- **Systolic**: [2181381000000109 |Average ambulatory systolic blood pressure (observable entity)|](https://termbrowser.nhs.uk/?perspective=full&conceptId1=2181381000000109)
- **Diastolic**: [2181391000000106 |Average ambulatory diastolic blood pressure (observable entity)|](https://termbrowser.nhs.uk/?perspective=full&conceptId1=2181391000000106)

These codes represent an average calculated from readings that have been taken over a period (such as 24 hours) which includes day and night intervals.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: NHS England will be requesting new parent SNOMED codes to complete the day interval/night interval triplets:
    <ul>
    <li>NEW CODE |Average ambulatory day interval blood pressure (observable entity)</li>
    <li>NEW CODE |Average ambulatory night interval blood pressure (observable entity)</li>
    </ul>
    In the interim period before the two new parent codes are created, suppliers are asked to ignore the following four codes:
    <ul>
    <li>2181401000000109 |Average ambulatory day interval systolic blood pressure (observable entity)</li>
    <li>2181411000000106 |Average ambulatory day interval diastolic blood pressure (observable entity)</li>
    <li>2181421000000100 |Average ambulatory night interval systolic blood pressure (observable entity)</li>
    <li>2181431000000103 |Average ambulatory night interval diastolic blood pressure (observable entity)</li>
    </ul>
    Once the two new parent codes are available,suppliers will be asked to begin sending and receiving the two complete day interval / night interval triplets.
</div>

Snippet (elements removed for brevity)

```xml
<Observation>
    ...
    <code>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="2181371000000107" />
            <display value="Average ambulatory blood pressure" />
        </coding>
        <text value="Average ambulatory blood pressure" />
    </code>
    ...
    <component>
        <code>
            <coding>
                <system value="http://snomed.info/sct" />
                <code value="2181381000000109" />
                <display value="Average ambulatory systolic blood pressure" />
            </coding>
            <text value="Average ambulatory systolic blood pressure" />
        </code>
        <valueQuantity>
            <value value="158" />
            <unit value="millimeter of mercury" />
            <system value="http://unitsofmeasure.org" />
            <code value="mm[Hg]" />
        </valueQuantity>
    </component>
    <component>
        <code>
            <coding>
                <system value="http://snomed.info/sct" />
                <code value="2181391000000106" />
                <display value="Average ambulatory diastolic blood pressure" />
            </coding>
            <text value="Average ambulatory diastolic blood pressure" />
        </code>
        <valueQuantity>
            <value value="102" />
            <unit value="millimeter of mercury" />
            <system value="http://unitsofmeasure.org" />
            <code value="mm[Hg]" />
        </valueQuantity>
    </component>
</Observation>
```

---