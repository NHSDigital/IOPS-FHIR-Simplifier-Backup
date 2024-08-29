## {{page-title}}

Providers must return all the columns as described in the table below, sorted by `Date` descending:

| Order | Name | Description | Value Details |
| --- | --- | --- | --- |
| 1   | `Date` | The date of the encounter | `dd-Mmm-yyyy` |
| 2   | `Title` | A short human-readable title for the encounter, to be composed of a subset of the `Practitioner` and `Organization` details linked to the encounter | `free-text` |
| 3   | `Details` | Longer human readable details for the encounter | `free-text` |