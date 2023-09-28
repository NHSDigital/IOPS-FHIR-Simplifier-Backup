## `identifier`

<b>Definition:</b>

**SHOULD** contain a professional code.

The inclusion of a professional code is strongly recommended. For consultants and doctors a prescribing code should be present. Please see [NHS Data Model and Dictionary](https://datadictionary.nhs.uk/) for details on these code.

The *SDS User Id* should be sourced from NHS Identity (SmartCard), this is also held within the Spine Directory Service LDAP database.

<table class="assets" style="overflow-wrap:anywhere;">
<thead>
<tr class="wordBreak">
<th width="15%">FHIR identifier</th>
<th width="10%">OID/HL7v3</th>
<th width="10%">HL7v2 ITK</th>
<th width="15%">Format</th>
<th width="20%">Description</th>
<th width="10%">Professional Code</th>
<th width="10%">Prescribing Code</th>
</tr>
</thead>
<tbody>
<tr>
<td class="wordBreak"><a href="https://fhir.hl7.org.uk/Id/gmp-number">https://fhir.hl7.org.uk/Id/gmp-number</a></td>
<td>2.16.840.1.113883.2.1.3.2.4.16.62</td>
<td>GMP</td>
<td>G[1234589]NNNNNN</td>
<td>General Medical Practitioner Code <a href="https://datadictionary.nhs.uk/attributes/general_medical_practitioner_ppd_code.html">GENERAL MEDICAL PRACTITIONER PPD CODE</a>. Formerly called GP General National Code (GNC).</td>
<td>Yes</td>
<td>No, also include DIN</td>
</tr>
<tr>
<td><a href="https://fhir.hl7.org.uk/Id/gmc-number">https://fhir.hl7.org.uk/Id/gmc-number</a></td>
<td>2.16.840.1.113883.2.1.3.2.4.16.63</td>
<td>GMC</td>
<td>CNNNNNNN</td>
<td>General Medical Council Code <a href="https://datadictionary.nhs.uk/attributes/consultant_code.html">CONSULTANT_CODE</a></td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td><a href="https://fhir.hl7.org.uk/Id/nmc-number">https://fhir.hl7.org.uk/Id/nmc-number</a></td>
<td></td>
<td></td>
<td>NNANNNNA</td>
<td>Nursing and Midwifery Council Code</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td><a href="https://fhir.hl7.org.uk/Id/gphc-number">https://fhir.hl7.org.uk/Id/gphc-number</a></td>
<td></td>
<td></td>
<td>NNNNNNN</td>
<td>General Pharmaceutical Council Code</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td><a href="https://fhir.hl7.org.uk/Id/hcpc-number">https://fhir.hl7.org.uk/Id/hcpc-number</a></td>
<td></td>
<td></td>
<td>AANNNNNN(*)</td>
<td>Health and Care Professional Council Code</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td><a href="https://fhir.hl7.org.uk/Id/din-number">https://fhir.hl7.org.uk/Id/din-number</a></td>
<td></td>
<td></td>
<td>NNNNNN</td>
<td><a href="https://datadictionary.nhs.uk/attributes/doctor_index_number.html">DOCTOR INDEX NUMBER</a></td>
<td>No</td>
<td>Yes</td>
</tr>
<tr>
<td><a href="https://fhir.nhs.uk/Id/sds-user-id">https://fhir.nhs.uk/Id/sds-user-id</a></td>
<td>1.2.826.0.1285.0.2.0.65</td>
<td></td>
<td>N(*)</td>
<td>SDS User ID</td>
<td>No</td>
<td>No</td>
</tr>
<tr>
<td><a href="https://fhir.nhs.uk/Id/gmc-reference-number">https://fhir.nhs.uk/Id/gmc-reference-number</a></td>
<td>2.16.840.1.113883.2.1.3.2.4.18.29</td>
<td></td>
<td>NNNNNNN</td>
<td><a href="https://www.datadictionary.nhs.uk/attributes/general_medical_council_reference_number.html">GMC Reference Number</a></td>
<td>No</td>
<td>No</td>
</tr>
<tr>
<td><a href="https://fhir.hl7.org.uk/Id/professional-code">https://fhir.hl7.org.uk/Id/professional-code</a></td>
<td>1.2.826.0.1285.0.2.1.54</td>
<td></td>
<td>A(*)</td>
<td>ODS/NACS Practitioner Code (retired). Included for backwards compatibility</td>
<td>No</td>
<td>No</td>
</tr>
</tbody>
</table>
<br>

Format
- N = any number
- A = any alpha

(*) NHS Prescription Services systems require these prescriber codes to be 8 characters long. Additional zeroes (0) should be inserted immediately following the first 2 alpha characters to extend the code to 8 characters as necessary.

<table class="assets">
<thead>
<tr>
<th>Code</th>
<th>Format</th>
<th>Example</th>
</tr>
</thead>
<tbody>
<tr>
<td>GP/medical prescriber (DIN)</td>
<td>NNNNNN</td>
<td>954000</td>
</tr>
<tr>
<td>Nurse prescriber (NMC)</td>
<td>NNANNNNA</td>
<td>71A2998E</td>
</tr>
<tr>
<td>Pharmacist prescriber (GPHC)</td>
<td>NNNNNNN</td>
<td>2033467</td>
</tr>
<tr>
<td>Optometrist prescriber</td>
<td>NN-NNNNN</td>
<td>01-09491</td>
</tr>
<tr>
<td>Podiatrist prescriber (HCPC)</td>
<td>CHNNNNNN</td>
<td>CH029821</td>
</tr>
<tr>
<td>Physiotherapist prescriber (HCPC)</td>
<td>PHNNNNNN</td>
<td>PH095159</td>
</tr>
<tr>
<td>Radiographer prescriber (HCPC)</td>
<td>RANNNNNN</td>
<td>RA088262</td>
</tr>
<tr>
<td>Dietician prescriber (HCPC)</td>
<td>DTNNNNNN</td>
<td>DT012345</td>
</tr>
<tr>
<td>Paramedic prescriber (HCPC)</td>
<td>PANNNNNN</td>
<td>PA054321</td>
</tr>
</tbody>
</table>

The *Doctor Index Number (DIN)* will be present in the resource even if they are prescribing using a different prescribing code. This code is called the *spurious code* is held within the `England-PractitionerRole` resource and **MUST NOT** be contained in the Practitioner resource. 

### Professional Code System (Unspecified/Unknown System)

In cases where the profession code is present but it is not certain what type of code this is, the `https://fhir.hl7.org.uk/Id/professional-code` system should be used. It is also used for backwards compatibilty with EPS HL7 v3 ODS/NACS Practitioner Identifiers.

This system may include codes from different codes and this may lead to identfication issues, for example GPhC and GMC Reference Number have the same format (7 digits), if one of these is receieved it is not known if this is a doctor and or a pharmacist.

<b>Comment:</b>

SHOULD contain a professional code or SDS-user-id.

### `identifier.gmpCode`

<b>Definition:</b>

Formerly called GP General National Code (GNC).

### `identifier:professionalNumber`

<b>Definition:</b>

A legacy system to support conversion of NPfIT/v3 CodeSysem to FHIR.

This should not be used on new implementations. More accurate systems such as https://fhir.hl7.org.uk/Id/gmp-number and https://fhir.hl7.org.uk/Id/gmc-number

Although this system was intended to only be ODS/NACS Practitioner Identifiers, it has been used as a general purpose system. Therefore the codes can't be trusted e.g. 1234567 could be referring to a GPhC (pharmacist) or GMC Reference Number (doctor). These codes on their won should not be considered safe for the purposes of Practitioner identification.

### `identifier:gmcReferenceNumber`

<b>Definition:</b>

This should not be confused with https://fhir.hl7.org.uk/Id/gmc-number which is the Consultants CONSULTANT_CODE.

This is considered a supplemental code and the official English NHS identifiers (https://fhir.hl7.org.uk/Id/gmc-number or https://fhir.hl7.org.uk/Id/gmp-number) should also be provided.

### `identifier:sdsUserId`

<b>Definition:</b>

Used with CIS2 and Spine.