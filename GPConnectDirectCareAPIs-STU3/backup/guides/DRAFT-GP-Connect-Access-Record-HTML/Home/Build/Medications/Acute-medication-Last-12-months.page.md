## {{page-title}}

#### Clinical narrative

A list of acute medicines that are currently being, or have recently been, used to treat or prevent disease for the patient. The provider **MUST** include all acute medication whose `Start Date` (the date the prescription is expected to start) is greater than the current date minus 365 days.

This is aligned to the Acute Medications section in Summary Care Records (SCR).

#### Purpose

The purpose of this section is to provide a view of acute medications that the patient has recently been taking, which informs the clinical decision-making process.

#### Subsection title

The subsection title **MUST** be ‘Acute Medication (Last 12 Months)’.

#### Date filter

All relevant records **MUST** be returned.

#### Subsection content banner

Provider message describing at a summary level how they have populated this subsection.

Providers **MUST** return the following message, if applicable:

```html
<div>
    <p>Scheduled End Date is not always captured in the source; where it was not recorded, the displayed date is calculated from start date and days duration</p>
</div>
```

#### Table columns

Providers **MUST** return all the columns as described in the table below, sorted by `Start Date` descending:

|Order|Name|Description|Value details|
|---|---|---|---|
|1|`Type`|Type of medication issued (for example, `Acute, Acute Post-Dated, Acute - [Prescribing Agency Type]`<sup><strong>1</strong></sup>).|`free-text`|
|2|`Start Date`|The date of issue of the acute medications, except where:<br><br>- the medication is post-dated it **MUST** be the post date<br>- the medication is prescribed elsewhere it **MUST** be the expected start date if known, else the entered date|`dd-Mmm-yyyy`|
|3|`Medication Item`|Descriptive name of medication item (including dosage) (for example, `Ibuprofen 400mg tablets`).|`free-text`|
|4|`Dosage Instruction`|Dosage instructions for the medication item. As a minimum, this **MUST** include:<br><br>- Dosage Rate<br>- Schedule (when / how often)<br><br>for example, `two to be taken daily`|`free-text`|
|5|`Quantity`|Quantity details for the medication item. As a minimum, this **MUST** include:<br><br>- Quantity<br>- Quantity unit<br><br>for example, `14 capsule`|`free-text`|
|6|`Scheduled End Date`|The date the prescription is expected to finish.|`dd-Mmm-yyyy`|
|7|`Days Duration`|Duration of medication issued in days.|`integer`|
|8|`Additional Information`|If the medication record includes the information, the following details **MUST** be included (each item **MUST** be separated with a line break):<br><br>- **`CONTROLLED DRUG`** label in **bold** text<br>- `CANCELLED:`  label with cancellation date and reason<br>- Reason for the medication<br>- Linked problems / diagnoses<br>- Other supporting information<br><br>The provider **MAY** include labels in addition to the ones specified to support additional text (for example, `Linked Problem : Ear Infection`).|`free-text`|

<sup><strong>1</strong></sup> Where the medication was Prescribed Elsewhere the prescribing agency (type of organisation responsible for authorising and issuing the medication) **MUST** be included with the Type, for example, ‘Acute – Dentist’. If the medication item is identifiable as prescribed elsewhere but the type of organisation who prescribed it is not recorded, then the Type **MUST** be returned as ‘Acute – Unknown Prescriber’.