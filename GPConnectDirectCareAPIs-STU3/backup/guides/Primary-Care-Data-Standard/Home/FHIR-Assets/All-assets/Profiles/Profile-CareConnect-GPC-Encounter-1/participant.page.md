## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

**Single participant**

This element **MUST** be populated with a reference to the practitioner that recorded the consultation on the system, with the `participant.type` having the value of `REC` (recorder) from the vocabulary.


**Multiple participants**

In the event of multiple participants - there should always be a "primary performer" - which is represented by the code `PPRF` from the [GP Connect Participant Type Value-set](https://fhir.nhs.uk/STU3/ValueSet/GPConnect-ParticipantType-1).

Additional participants (such as registrars, trainees, or other parties present), may also be referenced; however, the participation type should have the value of `PART`.

No other values of participation type should be used.

The `individual` **MUST** contain a reference to the respective Practitioner or Related Person of the participant.

<h5><ins>Example</ins></h5>

```xml
<participant>
	<type>
		<coding>
			<system value="https://fhir.nhs.uk/STU3/ValueSet/GPConnect-ParticipantType-1" />
			<code value="REC" />
		</coding>
		<text value="recorder" />
	</type>
	<period>
		<start value="2022-12-25" />
		<end value="2023-01-02" />
	</period>
	<individual>
		<identifier>
			<system value="https://fhir.hl7.org.uk/Id/gmc-number" />
			<value value="0054272" />
		</identifier>
	</individual>
</participant>
```

---