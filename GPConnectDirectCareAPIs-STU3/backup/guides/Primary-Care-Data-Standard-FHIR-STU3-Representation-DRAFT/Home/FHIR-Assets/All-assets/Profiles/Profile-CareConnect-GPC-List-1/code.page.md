## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory

<h5><ins>Guidance</ins></h5>

A codeable concept to represent the type of list being sent.

### For structural lists

The purpose of the list.

There are currently 9 possible purposes of a list in response to a query for a clinical area in GP Connect that will be represented by the following SNOMED codes.

|Purpose|SNOMED Code|SNOMED Preferred Term / List.title|
|---|---|---|
|Medications and medical devices|933361000000108|Medications and medical devices|
|Allergies and adverse reactions|886921000000105|Allergies and adverse reaction|
|Ended allergies|1103671000000101|Ended allergies|
|Immunisations|1102181000000102|Immunisations|
|List of consultations|1149501000000101|List of consultations|
|Problems|717711000000103|Problems|
|Uncategorised data|826501000000100|Miscellaneous record|
|Outbound Referrals|792931000000107|Outbound referral|
|Investigations|887191000000108|Investigations and Results|
|Diary Entries|714311000000108|Patient recall administration|

The above code for ‘Ended allergies’ should be used for resolved allergies.

### For lists used in consultations

**List(Consultation)**

- provide the SNOMED: [325851000000107 | Consultation encounter type (record artifact) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=325851000000107)


**List(Topic)**

- provide the SNOMED: [25851000000105 | Topic (EHR) (record artifact) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=25851000000105)

**List(Heading)**

- provide the SNOMED: [24781000000107 | Category (EHR) (record artifact) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=24781000000107)


<h5><ins>Example</ins></h5>

```xml
<code>
    <coding>
        <system value="http://snomed.info/sct" />
        <code value="25851000000105" />
        <display value="Topic (EHR) (record artifact)" /> 
    </coding>
</code>
```

---