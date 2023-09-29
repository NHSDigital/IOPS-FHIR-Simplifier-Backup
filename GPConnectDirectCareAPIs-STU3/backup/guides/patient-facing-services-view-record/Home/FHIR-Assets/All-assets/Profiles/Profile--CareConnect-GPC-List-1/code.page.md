## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

A codeable concept to represent the type of list being sent.

For example:

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