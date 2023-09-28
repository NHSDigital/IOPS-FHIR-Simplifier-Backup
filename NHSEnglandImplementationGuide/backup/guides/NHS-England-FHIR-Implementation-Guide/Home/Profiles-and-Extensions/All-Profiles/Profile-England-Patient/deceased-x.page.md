## `deceased[x]`

<b>Definition:</b>

The date and time on which a person died or is officially deemed to have died, if applicable and known.

It is a datetime in the format `yyyy-mm-ddTHH:MM:SS+HH:MM` or `yyyy-mm-dd`. Due to data quality issues on a small number of patients `yyyy-mm` and `yyyy` format may also be returned.

When a patient tagged as `very restricted` is retrieved, death date is removed from the response.

---