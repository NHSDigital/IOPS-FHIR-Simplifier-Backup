## {{page-title}}

The following triple will be used to represent an average reading from an ambulatory blood pressure monitoring (ABPM) device.

- **Header**: [314463006 | 24 hour blood pressure (observable entity) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=314463006)
- **Systolic**: [314449000 | Average 24 hour systolic blood pressure (observable entity) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=314449000)
- **Diastolic**: [314462001 | Average 24 hour diastolic blood pressure (observable entity) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=314462001)

These codes may not exactly represent cases where the average has been calculated from readings that have been taken over a period that is less than 24 hours; however, the full ABPM report, which includes all readings, will be shared with the GP for reference.

The rationale behind the usage of these codes is that they are a valid triple, and suppliers such as EMIS, TPP, and Numed (ABPM supplier) are in agreement over the use over these codes.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: NHS England will be requesting new SNOMED codes to represent an "average ambulatory blood pressure", and will require both pharmacy and GP suppliers to support the new SNOMED codes once they are active.
</div>


Snippet (elements removed for brevity)

```xml
<Observation>
    ...
    <code>
        <coding>
            <system value="http://snomed.info/sct" />
            <code value="314463006" />
            <display value="24 hour blood pressure" />
        </coding>
        <text value="24 hour blood pressure" />
    </code>
    ...
    <component>
        <code>
            <coding>
                <system value="http://snomed.info/sct" />
                <code value="314449000" />
                <display value="Average 24 hour systolic blood pressure" />
            </coding>
            <text value="Average 24 hour systolic blood pressure" />
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
                <code value="314462001" />
                <display value="Average 24 hour diastolic blood pressure" />
            </coding>
            <text value="Average 24 hour diastolic blood pressure" />
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