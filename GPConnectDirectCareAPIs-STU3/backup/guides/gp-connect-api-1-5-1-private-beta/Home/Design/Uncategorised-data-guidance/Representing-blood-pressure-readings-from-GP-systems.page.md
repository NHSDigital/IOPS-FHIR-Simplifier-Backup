## {{page-title}}

Blood pressure is one of the most common observations that is recorded in GP records. 

There are over 70 million blood pressures recorded in general practice every year. As this is the case there is a desire to represent the various blood pressure concepts that are recorded in a common format wherever possible. In the majority of cases there are two components that comprise a blood pressure reading regardless of the type of reading. 

These are a systolic blood pressure reading and a diastolic blood pressure reading. In many cases these are also recorded as a triple with a heading or panel concept.


### The FHIR vital sign blood pressure profile

This version of GP Connect does not support the ‘vital signs’ aspect of the FHIR specification as there is currently no consensus in the UK as to what is/isn’t a vital sign.

However, the way we have represented blood pressures is based on the FHIR vital signs blood pressure profile [http://hl7.org/fhir/STU3/bp.html](http://hl7.org/fhir/STU3/bp.html). The profile uses a loinc "magic code" to flag certain blood pressures as vital signs. We are not currently using this flag in GP Connect.

Where possible blood pressures exported via GP Connect though will be exported using the same structure as the vital signs blood pressure profile. They **MUST** always use the same units, `mm[Hg]` whether exported in the triple structure or as individual observations.

GP Connect has improved the consistency of the data that will be exported, it is however the responsibility of the consuming system to interpret the blood pressure codes they recieve regardless of whether they are in a triple structure or as individual observations.

### Standard blood pressure representation
The way standard blood pressures are recorded in different clinical systems varies. These can be described by the following 3 different patterns:

- recorded as the following tripe in the below structure and using any of the codes from the table below

<div align="center">
{{ render: BP_Triple.png }}
</div>

- recorded as 2 individual readings that are grouped together with no panel code using any of the systolic and diastolic codes from the table below

<div align="center">
{{ render: BP_ComponentCodes.png }}
</div>


Where there is no panel code then [163020007 | On examination - blood pressure reading (finding) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=163020007) **MUST** be used in the GP Connect triple.

- recorded using a panel code with two readings but no systolic and diastolic codes. This may be recorded as either of the 2 panel codes from the table below

<div align="center">
{{ render: BP_HeaderCodeNoComponent.png }}
</div>

Where there is only a panel code the following codes **MUST** be used to complete the triple for export in GP Connect, [163020007 | On examination - blood pressure reading (finding) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=163020007) and [386534000 | Arterial blood pressure (observable entity) |](https://termbrowser.nhs.uk/?perspective=full&conceptId1=386534000)

In GP Connect we have decided that all of these variations will be represented using the triple structure in order to make the representation more uniform.

Following the guidance above to determine the appropriate codes for the triple will result in the following structure which may contain any of the codes from the table below

<div align="center">
{{ render: BP_Diagram.png }}
</div>

The triple may contain any combination of the following SNOMED codes for the panel, systolic and diastolic components.

<table class="nhsd-!t-margin-bottom-6">
    <thead>
        <tr>
            <th data-no-sort>Panel code</th>
            <th data-no-sort>Systolic blood pressure code</th>
            <th data-no-sort>Diastolic blood pressure code</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=163020007">163020007 | On examination - blood pressure reading (finding) |</a></td>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=72313002">72313002 | Systolic arterial pressure (observable entity) |</a></td>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=1091811000000102">1091811000000102 | Diastolic arterial pressure (observable entity) |</a></td>
        </tr>
        <tr>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=386534000">386534000 | Arterial blood pressure (observable entity) |</a></td>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=271649006">271649006 | Systolic blood pressure (observable entity) |</a></td>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=271650006">271650006 | Diastolic blood pressure (observable entity) |</a></td>
        </tr>
        <tr>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=75367002">75367002 | Blood pressure (observable entity) |</a></td>
            <td><a href=""></a></td>
            <td><a href=""></a></td>
        </tr>
    </tbody>
</table>

Where there is only a single component value recorded then the triple MUST still be represented using the relevant 3 codes with the component representing the missing reading containing the relevant dataAbsentReason code.

### Blood pressure readings that will be in the same structure

The table contains other blood pressure readings that **MUST** always be represented when exported from GP Connect as triples in line with the simple blood pressure format.

<table class="nhsd-!t-margin-bottom-6">
    <thead>
        <tr>
            <th data-no-sort>Panel code</th>
            <th data-no-sort>Systolic blood pressure code</th>
            <th data-no-sort>Diastolic blood pressure code</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=163020007">163020007 | On examination - blood pressure reading (finding) |</a></td>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=400974009">400974009 | Standing systolic blood pressure (observable entity) |</a></td>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=400975005">400975005 | Standing diastolic blood pressure (observable entity) |</a></td>
        </tr>
        <tr>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=400975005">400975005 | Standing diastolic blood pressure (observable entity) |</a></td>
            <td><a href=""><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=400974009">400974009 | Standing systolic blood pressure (observable entity) |</a></a></td>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=400975005">400975005 | Standing diastolic blood pressure (observable entity) |</a></td>
        </tr>
        <tr>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=163033001">163033001 | Lying blood pressure (observable entity) |</a></td>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=407556006">407556006 | Lying systolic blood pressure (observable entity) |</a></td>
            <td><a href="https://termbrowser.nhs.uk/?perspective=full&conceptId1=407557002">407557002 | Lying diastolic blood pressure (observable entity) |</a></td>
        </tr>
    </tbody>
</table>

In addition to the triples that have been defined here any blood pressure that is recorded as a triple within the GP clinical system MUST always follow this structure.

### Blood pressure readings with no defined triples

Where the blood pressure reading has not been defined here and is not recorded in the local system as a triple then these will be exported as individual observations. These observations MUST be linked using the ‘related’ element with a value of ‘has-member’ where they are recorded as a pair but with no panel code.

---
