## {{page-title}}

<table data-responsive class="nhsd-!t-margin-bottom-6">
    <thead>
        <tr>
            <th data-no-sort>DataType</th>
            <th data-no-sort>Optionality</th>
            <th data-no-sort>Cardinality</th>
        </tr>
    </thead>
    <tbody>
      <tr>
        <td>Period</td>
        <td>Required</td>
        <td>0..1</td>
      </tr>
    </tbody>
</table>

The period the medication or medical device is authorised under this medication/medical device plan. For items that are repeats and repeat dispensed this refers to the entire cycle of prescriptions made under the authorisation. For acutes, this refers to the period of the prescription issue.

`effectivePeriod.start` is **mandatory**

The date from which the medication or medical device is authorised under this plan.

Use one of the following dates in order of descending preference:

* the authorised date as recorded in the patient record

    * for authorisation that were performed during a consultation this will be the date when the consultation took place

* the date of the first issue under the medication/medical device plan
* the date the medication/medical device plan was recorded onto the system (the audit date)

`effectivePeriod.end` is **required**

The date when the authorisation under this plan ends.

Where the medication/medical device plan is still active, set to **null**.

Where the medication/medical device plan has ended use one of the following dates in order of descending preference:

* the end date recorded in the patient record

* the end date of the final issue under the medication/medical device plan. This is the start date of the final issue plus the expected supply duration.

* the date the plan was updated to ended

* the Period.start date

* this option should only occur where data has been lost (for example, during the record transfer between two systems) and is used to ensure that an ended plan will always have an end date

### Example
```json
    "effectivePeriod": {
      "start": "2022-10-23T13:50:00+00:00",
      "end": "2023-01-10T13:50:00+00:00"
    },
```

---