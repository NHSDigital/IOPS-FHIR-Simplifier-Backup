## {{page-title}}

### Clinical narrative
Any other inactive issue that was significant to a patient and affected their health or wellbeing. It includes disease, surgery and social issues such as bereavement or unemployment.

### Purpose
The purpose of this section is to provide information about a patient’s previous non-major problems and issues which may have informed the clinical decision-making process.

### Subsection title
The subsection title **MUST** be ‘Other Inactive Problems and Issues’.

### Date filter
A date filter is applicable for the ‘Other Inactive Problems and Issues’ subsection.

### Subsection content banner
Provider message describing at a summary level how they have populated this subsection.

### Table columns
Providers must return all the columns as described in the table below, sorted by `End Date` descending:

| Order | Name | Description | Value details |
| --- | --- | --- | --- |
| 1   | `Start Date` | The start date of the problem | `dd-Mmm-yyyy` |
| 2   | `End Date` | The end date of the problem | `dd-Mmm-yyyy` |
| 3   | `Entry` | A short human-readable title for the problem | `free-text` |
| 4   | `Significance` | The significance of the problem | `free-text` |
| 5   | `Details` | Longer human readable details for the problem | `free-text` |

Provider systems having 3 levels of significance **MUST** include inactive problems with the lowest level of significance in this subsection. If more than 3 levels of significance, then those less than the mid-level significance must be included in this subsection. Any inactive problems which do not have a significance level **MUST** be included in this section.

Provider systems not supporting inactive problems **MUST** display a message in the section banner to indicate:

- inactive problems are not supported as in the HTML Implementation Guide - Not Supported section
- that any problems and issues recorded for the patient are included in the ‘Active Problems and Issues’ subsection

Provider systems that support inactive problems, but when no records exist for the requested patient, **MUST** display the standard HTML implementation guide - supported but hasn’t been recorded message.