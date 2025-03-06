## {{page-title}}

#### Clinical narrative

A list of repeat drugs or other forms of medicines that are currently being used to treat or prevent disease for the patient. This may also include PRN occasional use medication - for example, EpiPen, antihistamines, monitoring or continence products.

The provider **MUST** include all repeat and repeat dispensed medications (templates/plans/courses **NOT** individual issues) which have not been discontinued or otherwise ended. Repeat medications (including repeat dispense) which have not been discontinued are considered current where the Effective End Date (the date the cycle of prescriptions is expected to end) is either greater than the current date or is null. This **MUST** include those which have been authorised but not yet issued (Last Issued and Number Issued will be null).

#### Purpose

The purpose of this section is to provide a view of all repeat medications that the patient is currently prescribed, which informs the clinical decision-making process.

This is aligned to the Repeat Medications section in Summary Care Records (SCR).

#### Subsection title

The subsection title **MUST** be ‘Current Repeat Medication’.

#### Date filter

All relevant records **MUST** be returned (that is, no time limit/filtering is to be applied).

#### Subsection content banner

Provider message describing at a summary level how they have populated this subsection.

Providers **MUST** return the following message, if applicable:

```html
<div>
    <p>The Review Date is that set for each Repeat Course. Reviews may be conducted according to a diary event which differs from the dates shown</p>
</div>
```

#### Table columns

Providers **MUST** return all the columns as described in the table below, sorted by `Start Date` descending:

|Order|Name|Description|Value details|
|---|---|---|---|
|1|`Type`|Type of medication issued (for example, `Repeat, Repeat Dispense, Repeat – [Prescribing Agency Type]`).|`free-text`|
|2|`Start Date`|The original date of authorisation of the repeat medication (if a provider system allows re-authorisation of a repeat medication the start date **MUST** be the first authorisation). If this is not known (for example, for prescribed elsewhere) then date of entry of the repeat medication record **MUST** be returned.|`dd-Mmm-yyyy`|
|3|`Medication Item`|Descriptive name of medication item (including dosage) (for example, `Ibuprofen 400mg tablets`).|`free-text`|
|4|`Dosage Instruction`|Dosage instructions for the medication item. As a minimum, this **MUST** include:<br><br>- Dosage Rate<br>- Schedule (when / how often)<br><br>for example, `two to be taken daily`|`free-text`|
|5|`Quantity`|Quantity details for the medication item. As a minimum, this **MUST** include:<br><br>- Quantity<br>- Quantity unit<br><br>for example, `14 capsule`|`free-text`|
|6|`Last Issued Date`|The last issue date. If the medication is repeat dispense or prescribed elsewhere this **MUST** be null.|`dd-Mmm-yyyy`|
|7|`Number of Prescriptions Issued`|This **MUST** be the number issued up to the current date inclusive. For a repeat dispense this will be null. This **MUST** be null where no issues of the repeat have been made at the current date. If the medication is repeat dispensed or prescribed elsewhere this **MUST** be null.|`integer`|
|8|`Max Issues`|The maximum number of issues the repeat prescription has authorised.|`integer`|
|9|`Review Date`|The date the repeat medication is due for review.|`dd-Mmm-yyyy`|
|10|`Additional Information`|If the medication record includes the information, the following details **MUST** be included (each item **MUST** be separated with a line break):<br><br>- **`CONTROLLED DRUG`** label in **bold** text<br>- Reason for the medication<br>- Linked problems / diagnoses<br>- For Repeat Dispense, the date of the last authorisation and the number of prescription issues authorised<br>- Other supporting information<br><br>The provider **MAY** include labels in addition to the ones specified to support additional text (for example, `Linked Problem : Heart Failure`).|`free-text`|

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
<i class="fas fa-exclamation-circle text-primary"></i> <b>Note: </b> If the provider system allows the repeat medication (course/template) details to be amend so it differs from the latest prescription issued, then:
<ul><li>the latest details for the medication (course/template) <strong>MUST</strong> be returned by the provider</li><li>a subsection banner message <strong>MUST</strong> be added such as: the medication below is taken from a list of Repeat Medication Templates in the patient record which may have been amended since they were last issued. See the All Medication Issues subsection for all repeat prescriptions issued.</li></ul>
</div>