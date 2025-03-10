## {{page-title}}

The following applies to the presentation of any component part of the dosage instruction;

- In most cases, express numbers as numbers, e.g. `3` not `three`. There are suggested exceptions:
  - Refer to the section below when dealing with `frequency` data for the case of `once` or `twice`.
  - When a proceeding unit of measure starts with a number, e.g. `5ml spoonful` separate the quantity from the unit of measure with a `x` symbol, e.g. `2 x 5ml spoolful`. Alternatively when the quantity is `1` or `2` is may be preferrable to express the quantity in words, e.g. `ONE` or `TWO`, e.g. `TWO 5ml spoonful`. Both options prevent misreading as a `25ml spoonful`.
  - Where a decimal number, e.g. `0.5` **AND** the unit of measure is **NOT** an [SI unit](https://www.nist.gov/pml/owm/metric-si/si-units) **AND** the quantity is N.25, N.5 or N.75, then express using the words `quarter`, `half` or `three quarters`, e.g. `half tablet`, otherwise express as a decimal number, e.g. `12.5 milligram`.

- Always express units of measure using the full description, e.g. `milligram` not `mg`. An exception is when the unit of measure as part of a pre-coordinated dm+d concept descriptions, e.g. `Ramipril 5mg capsules`.

- Always express a time-based unit of measure in the plural when applicable, e.g. `2 hour` becomes `2 hours`.

- **Do not** express other units of measure in the plural as this introduces complications with units such as `microgram per millilitre` or `microgram per kilogram per hour`.

- Separate multiple `when` statements with a comma plus whitespace. FHIR intreprets multiple `when` events as the union of these events so no extra textual expression is required. For example, if `when=NORM` and `when=C` then express as `during the morning, at a meal`.

- Separate multiple `events` statements with a comma plus whitespace. As these are separate events, for a more readable dosage instruction, consider replacing the last comma separating the final two statements with the word " and ", e.g. `on 25/01/2019, 25/02/2019 and 25/03/2019`.

---