## {{page-title}}

Providers must return all the columns as described in the table below, sorted by `Date` descending:

| Order | Name | Description | Value details |
| --- | --- | --- | --- |
| 1   | `Date` | The date of entry of the clinical item | `dd-Mmm-yyyy` |
| 2   | `Entry` | A short human readable title for the clinical item | `free-text` |
| 3   | `Details` | Longer human readable details for the clinical item | `free-text` |

The provider **MAY** include or exclude items which are included in the observations view. If ‘observations’ are included, all the details which are included in the Value, Range and Details columns in the observations view **MUST** be included in the Details column of this view.

