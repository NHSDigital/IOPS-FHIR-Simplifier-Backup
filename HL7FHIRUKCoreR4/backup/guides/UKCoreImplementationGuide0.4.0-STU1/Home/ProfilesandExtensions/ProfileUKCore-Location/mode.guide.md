## `mode`

The Location.mode element can be used to indicate whether a Location resource represents a specific (potentially identifiable) Location (`instance`), or a class of Locations (`kind`). Especially Resources capturing orders, resource scheduling, plans and definitions may refer to Locations in `kind` mode. For these domains, it is often not necessary to refer to a specific Location, but rather to a class of Locations. An example of this is found in planning, where we need to allocate an "isolation room" for a patient, or need to dispatch "an ambulance" at a certain time. In these cases it is not important exactly which isolation room or ambulance is allocated, and it is sufficient to just indicate a `kind` of Location.

Note that `kind` should not be used to represent Locations where an actual instance of a Location was involved, but identifying information is missing. E.g. when a patient arrived 'by ambulance', but it is not known by which ambulance, this should be represented using a Location in `instance` mode with a missing identifier, not a Location of `kind` ambulance.

Some of Location's data elements are only relevant when mode is `instance` and should not be used when mode is `kind`:
(however this information could still be included if was relevant, such as when it is a generic item, but not globally generic, e.g. a Burgers MU ambulance).

---
