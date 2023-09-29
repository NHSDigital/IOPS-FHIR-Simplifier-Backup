## Element: `identifier` <span class="mro-circle mandatory" title="Mandatory"></span>

Use if a local implementation requires bespoke identifiers to track medication requests between the ePMA and pharmacy systems.


<!-- sentance as to why this is mandatory -->
This will allow x-referencing for a `MedicationRequest` to be uniquely identified within a pharmacy system, and this is the id that you use when referencing a med request within a `MedicationDispense`. This is fundamental to the cross referencing.

---