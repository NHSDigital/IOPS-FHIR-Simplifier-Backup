## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle mandatory" title="Mandatory"></span> Mandatory


<h5><ins>Guidance</ins></h5>

A reference to the subject matter for which the Flag relates to.

- Reference can be any of the following - (Group | PlanDefinition | Procedure | CareConnect-Patient-1 | CareConnect-Organization-1 | CareConnect-Practitioner-1 | CareConnect-Location-1 | CareConnect-Medication-1)

<i class="fa fa-link"></i> {{pagelink:Home/FHIR-Assets/All-assets/Profiles/Profile--CareConnect-GPC-Patient-1}}

<h5><ins>Example</ins></h5>

```xml
<subject>
	<identifier>
		<extension
			url="https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-NHSNumberVerificationStatus-1">
			<valueCodeableConcept>
				<coding>
					<system
						value="https://fhir.hl7.org.uk/STU3/CodeSystem/CareConnect-NHSNumberVerificationStatus-1" />
					<code value="01" />
					<display value="Number present and verified" />
				</coding>
				<text value="Number present and verified" />
			</valueCodeableConcept>
		</extension>
		<system value="https://fhir.nhs.uk/Id/nhs-number" />
		<value value="9989453456" />
	</identifier>
</subject> > 
```

---