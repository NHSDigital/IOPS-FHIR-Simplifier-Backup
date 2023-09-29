## Element: `requester` <span class="mro-circle mandatory" title="Mandatory"></span>

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong>Recommendations</strong>: 
    <ul>
        <li>should be a required business element for most MVP implementations</li>
        <li>should be the prescriber recorded on the ePMA system for the medication request</li>
        <li>should implement as a reference a FHIR Practitioner resource.</li>
    </ul>
</div>

Where an implementation requires the identification of a person plus an organisation then the solution differs depending on the version of FHIR. Within an `R4` implementation replace the `Practitioner` resource with a `PractitionerRole` resource.

The previous `STU3` version required the inclusion of a `requester.onBehalfOf` element. 

---