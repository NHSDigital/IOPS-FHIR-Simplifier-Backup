## {{page-title}}

Providers **MUST** return all the columns as described in the table below, sorted by `Date` descending:

| Order | Name | Description | Value details &nbsp;&nbsp;&nbsp; |
| ------------ | ------------ | ------------ |
| 1 | `Date`  <em class="fa fa-sort-desc" aria-hidden="true">| The date of the administrative item | `dd-Mmm-yyyy` |
| 2 | `Entry` | A short human readable free-text title for the administrative item | `free-text` |
| 3 | `Details` | Longer human readable details for the administrative item, codes such as READ or SNOMED **MUST NOT** be included. | `free-text` |

The provider **MAY** include or exclude items which are included in the [observations](accessrecord_view_observations.html) view.
If 'observations' are included, all the details which are included in the Value, Range and Details columns in the observations view **MUST** be included in the Details column of this view.