## {{page-title}}

### Clinical narrative
Any major inactive issue that was significant to a patient and affected their health or wellbeing. It includes disease, surgery and social issues such as bereavement or unemployment.

### Purpose
The purpose of this section is to provide information about a patient’s previous significant problems and issues which may have informed the clinical decision-making process.

### Subsection title
The subsection title **MUST** be ‘Major Inactive Problems and Issues’.

### Date filter
A date filter is applicable for the ‘Major Inactive Problems and Issues’ subsection.

### Subsection content banner
Provider message describing at a summary level how they have populated this subsection.

### Table columns
Providers must return all the columns as described in the table below, sorted by `End Date` descending:

| Order | Name | Description | Value details |
| --- | --- | --- | --- |
| 1   | `Start Date` | The start date of the problem | `dd-Mmm-yyyy` |
| 2   | `End Date` | The end date of the problem | `dd-Mmm-yyyy` |
| 3   | `Entry` | A short human-readable title for the problem | `free-text` |
| 4   | `Significance` | The significance of the problem (meaning, Major or Minor) | `free-text` |
| 5   | `Details` | Longer human readable details for the problem | `free-text` |

Provider systems having 3 levels of significance **MUST** include inactive problems with the highest and mid-level significance in this subsection. If more than 3 levels of significance, then those equal to or greater than the mid-level significance **MUST** be included in this subsection. Provider systems **MUST NOT** include problems without a significance level in this subsection (for example, if significance is not mandatory and has not be recorded).

Provider systems supporting inactive problems but not supporting clearly defined significance levels **MUST** return all inactive problems in the ‘Other Problems and Issues’ subsection, and **MUST**:

- return a subsection content banner to indicate that any inactive problems are included in the ‘Other Problems and Issues’ subsection
- return an error message in place of the subsection table as detailed in the HTML Implementation Guide - Not Supported section

Systems not supporting inactive problems **MUST**:

- return an error message in place of the subsection table as detailed in the HTML Implementation Guide - Not Supported section
- display a message in the section banner to indicate that any problems and issues recorded for the patient are included in the ‘Active Problems and Issues’ section

Provider systems that support major inactive problems, but when no records exist for the requested patient, **MUST** display the standard HTML implementation guide - supported but hasn’t been recorded message.

