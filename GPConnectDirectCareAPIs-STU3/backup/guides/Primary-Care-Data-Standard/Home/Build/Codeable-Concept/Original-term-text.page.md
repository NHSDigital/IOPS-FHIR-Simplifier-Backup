## {{page-title}}

### Storage

When processing an item, the receiving system **MUST** always store the original term text of
the item. That is, the text chosen/manually entered by the clinician/user to describe the item
they are recording. Failure to do this could result in the intended meaning of the item being
altered.

The original term text will be available in one of the following fields in order of descending
priority:
1. text
1. coding.descriptionDisplay where userSelected = TRUE (or is unpopulated, and only
one coding element is present)
1. coding.display where userSelected = TRUE (or is unpopulated, and only one coding
element is present)

Where the receiving system can derive the original term text from the clinical code and the
derived text is lexically identical to the original term text, then the receiving system is not
required to store the text separately.

However, where the system supports SNOMED CT codes it MUST store any SNOMED CT
codes associated with the item where the userSelected is set to ‘TRUE’ and propagate these
onward in any future export of the data. As noted in section 3.1, some SNOMED CT codes
received may be from a release or extension of SNOMED not available on the receiving
system.

### Display

When displaying an item to end users, the receiving system **MUST** always display the original
term text of the item.

### Propagation

When propagating an item to another system, the receiving system **MUST** always include the
original term text of the item.