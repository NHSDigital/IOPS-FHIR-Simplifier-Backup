## {{page-title}}

Although FHIR provides some context around the intent, it does not always make it clear to the receiver what the intent from the sender was.

Using allergies as an example.

- a pharmacist may ask a patient whether they have any allergies
- the patient states they are allergic to tree and grass pollen (hayfever)
- the pharmacist records this onto their clinical system
- the pharmacist may decide to relay that information onto the GP system


Once the GP receives this information, they need to perform the following options:

- validate that the contents of the FHIR payload is valid
- interrogate their internal patient record and pull out the list of allergies

The GP system now needs to apply some sort of business logic to determine the following:

- Is the allergy already known?
- If it is - should it be updated?
- If it isn't - does the GP 'trust' the sender well enough to add it to the patient record?
- Should it be added as unverified?

Even if that was worked out, there are additional edges cases that need to be thought about:

- What if the sender makes a mistake and sends an update to say that allergy was incorrect and needs to be removed?
- What if the GP has acted on the first message and arranged an appointment with the patient to discuss their allergy in greater detail?

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    These scenarios need to be fully understood, and clinically-led guidance needs to be created so that receivers know what to do with these type of updates - not just for allergies, but other types of information too.
</div>


---
