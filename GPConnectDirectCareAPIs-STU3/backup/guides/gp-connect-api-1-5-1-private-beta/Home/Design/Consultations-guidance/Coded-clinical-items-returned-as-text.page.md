## {{page-title}}

The provider **MUST** return the following items as text, where they are contained in returned consultations, as they are not covered by the clinical areas defined in this specification version

- Completed diary entries
- Test requests (which are not in scope of investigations)

These must be returned in an `Observation` resource in the same manner as a comment note and as defined in the uncategorised data profile. The returned resource must represent the full text as presented in the GP system, including notes and qualifiers, not just the code description.

---