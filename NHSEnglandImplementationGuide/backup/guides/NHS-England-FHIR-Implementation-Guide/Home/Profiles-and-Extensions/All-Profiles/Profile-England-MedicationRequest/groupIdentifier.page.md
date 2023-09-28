## `groupIdentifier`

<b>Definition</b><br>

The purpose of the Short Form Prescription ID is to identify the prescription during its lifecycle within the Spine (i.e. prescribe, dispense  claim). The prescription UUID is retained to provide the link through to the Spine medication record within the PSIS and must be included as the first identifier within the prescription message.


The format of the Short Form Prescription ID is as follows:

- `RandomNumber`
- `PracticeODSCode/ClinicODSCode`
- `PracticeSequence/ClinicSequence`
- `CheckDigit`

Where;

 `RandomNumber` is a locally generated random number each time a Prescription ID is generated of length 6 hexadecimal characters.

`PracticeODSCode/ClinicODSCode` is the unique ODS code for the practice or clinic code (aka cost centre) as defined within the Spine SDS of length 6 characters. Where the prescriber ODS code is shorter than 6 characters it must be zero-padded up to six characters from the start of the ODS code, e.g. “0A1B2C”.

`PracticeSequence/ClinicSequence` is an incremental sequence number starting from 00000 that is reset after FFFFF back to zero of length 5 hexadecimal characters. For systems that support multiple practices or clinics, a sequence number per practice/clinic is required. This is to ensure uniqueness of prescriptions within the Spine EPS component during the prescription lifecycle.

`CheckDigit` is calculated on the entire ID using the ISO/IEC 7064:2003 MOD 37-2 standard. The check digit algorithm is identical to that using for EPS Release 1.

Note. Hyphens are always included to separate the ID into 3 blocks of 6 characters.

Note. The implementation of the MOD 37-2 standard uses a “+” character for char 36 opposed to a “*” character.

Short Form Prescription ID example (for illustration purposes only):
**83C40E-A23856-00123W**

### `groupIdentifier.extension:PrescriptionOrderUUID`

UUID order number for grouped MedciationRequests

When UUIDs are used within HL7 messages they must be represented in an upper case human-readable hexadecimal format where hyphen separators are used as per the example below and as defined by the ‘datatype’ schema within the DMS.

UUID example (for illustration purposes only **34026084-A445-84AD-2D01-97D69ED25865**.

---