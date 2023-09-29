## {{page-title}}

#### Example wireframe

<div class="nhsd-!t-margin-bottom-8 nhsd-t-text-align-center">
{{render: gpc-consultation-summary-report-pdf-layout-example.png }}
</div>

#### Field descriptions

<table data-responsive>
  <thead>
    <tr>
      <th data-no-sort>Field name</th>
      <th data-no-sort>Description</th>
      <th data-no-sort>Confidential</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><code>Version [x]</code></td>
      <td>The version of the consultation report sent.</td>
      <td style="text-align: center"><i class="fas fa-check text-success" /></td>
    </tr>
    <tr>
      <td><code>Number of related documents</code></td>
      <td>The number of documents attached to the message - for example, pain-point diagram, ECG, photo. These will be all documents recorded on the GP system that are linked to the consultation.</td>
      <td style="text-align: center"><i class="fas fa-check text-success" /></td>
    </tr>
    <tr>
      <td><code>Page [x] of [y]</code></td>
      <td>The page number and total pages of the PDF.</td>
      <td style="text-align: center"><i class="fas fa-check text-success" /></td>
    </tr>
    <tr>
      <td><code>Patient Name</code></td>
      <td>The surname, forename(s) and title of the patient. <br>Format all names in the document as follows:<br /><br /><code>SURNAME &lt;uppercase&gt;, Forename(s), (Title)</code><br /><br />This may wrap over multiple lines depending on the length of the name.</td>
      <td style="text-align: center"><i class="fas fa-check text-success" /></td>
    </tr>
    <tr>
      <td><code>DOB</code></td>
      <td>The date of birth of the patient in the format: <code>dd-MMM-yyyy</code></td>
      <td style="text-align: center"><i class="fas fa-check text-success" /></td>
    </tr>
    <tr>
      <td><code>NHS No</code></td>
      <td>The NHS Number of the patient in the format <code>### ### ####</code></td>
      <td style="text-align: center"><i class="fas fa-check text-success" /></td>
    </tr>
    <tr>
      <td><code>Tel No</code></td>
      <td>The patient’s contact telephone number.<br> Format all telephone numbers in the document as follows:<br /><br /><code>Area Code &lt;space&gt; Local Number [‘x’ Extension Number]</code> <br/><br />For local numbers with more than six digits include a space before the final four digits.</td>
      <td style="text-align: center"><i class="fas fa-check text-success" /></td>
    </tr>
    <tr>
      <td><code>Mobile No</code></td>
      <td>The patient’s contact mobile telephone number.</td>
      <td style="text-align: center"><i class="fas fa-check text-success" /></td>
    </tr>
    <tr>
      <td><code>Current Tel No</code></td>
      <td>If the patient is currently staying at a temporary location, the number(s) for contacting the patient at that location. If the patient is not at a temporary location this will be blank and the ‘Current Tel No.’ label will not be shown.</td>
      <td style="text-align: center"><i class="fas fa-check text-success" /></td>
    </tr>
    <tr>
      <td><code>Home/Registered Address</code></td>
      <td>The registered address of the patient, presented line by line, including postcode. This may wrap over multiple lines depending on the length of the address.</td>
      <td style="text-align: center"><i class="fas fa-check text-success" /></td>
    </tr>
    <tr>
      <td><code>Current Address</code></td>
      <td>If the patient is currently staying at a temporary location, the address of that location. If the patient is not at a temporary location this will be blank and the ‘Current Address’ label will not be shown.</td>
      <td style="text-align: center"><i class="fas fa-check text-success" /></td>
    </tr>
    <tr>
      <td><code>Clinician</code></td>
      <td>The full name and role of the treating clinician for the consultation. Where the consultation has been set to confidential the data from the consultation is not displayed.</td>
      <td style="text-align: center"><i class="fas fa-times text-danger" /></td>
    </tr>
    <tr>
      <td><code>Tel No</code></td>
      <td>The main telephone number of the organisation. Where the consultation has been set to confidential the data from the consultation is not displayed.</td>
      <td style="text-align: center"><i class="fas fa-times text-danger" /></td>
    </tr>
    <tr>
      <td><code>Email</code></td>
      <td>The main email address of the organisation. Where the consultation has been set to confidential the data from the consultation is not displayed.</td>
      <td style="text-align: center"><i class="fas fa-times text-danger" /></td>
    </tr>
    <tr>
      <td><code>Branch Location</code></td>
      <td>The name of the branch location, if applicable. Where the consultation has been set to confidential the data from the consultation is not displayed. If Branch Location is not applicable then the label will not be shown.</td>
      <td style="text-align: center"><i class="fas fa-times text-danger" /></td>
    </tr>
    <tr>
      <td><code>Organisation</code></td>
      <td>The name of the organisation and the town specified in its full address. Where the consultation has been set to confidential the data from the consultation is not displayed.</td>
      <td style="text-align: center"><i class="fas fa-times text-danger" /></td>
    </tr>
    <tr>
      <td><code>Consultation Date</code></td>
      <td>The date and time of the patient’s appointment at the sending organisation in the format: <code>dd-MMM-yyyy hh:mm</code></td>
      <td style="text-align: center"><i class="fas fa-check text-success" /></td>
    </tr>
    <tr>
      <td><code>Receiving GP Practice</code></td>
      <td>The name of the GP practice receiving the consultation report.</td>
      <td style="text-align: center"><i class="fas fa-check text-success" /></td>
    </tr>
    <tr>
      <td><code>Summary Reason</code></td>
      <td>A brief description of why the consultation report has been sent to the receiving GP practice entered into the [Summary Reason] section of the PDF document.<br /><br /> The text <strong>MUST</strong> be:<br /><code>A patient recently consulted with a clinician at an organisation different to the GP practice that they are registered with. The notes contained in this document are a summary of the consultation.</code></td>
      <td style="text-align: center"><i class="fas fa-times text-danger" /></td>
    </tr>
    <tr>
      <td><code>Clinical note section title</code></td>
      <td>The title of the clinical section being displayed.</td>
      <td style="text-align: center"><i class="fas fa-check text-success" /></td>
    </tr>
    <tr>
      <td><code>[notes]</code></td>
      <td>All data entered by the clinician at the sending organisation into the <code>[notes]</code> section of the PDF document. This includes all free text, clinical/SNOMED CT codes, dm+d codes and any other data entered relating to the consultation.<br /><br />This data must be displayed in a format that matches how the consultation is displayed on screen or when printed. Each section must have a title in bold text.<br /><br />There must be a carriage return after each section to make the document more easy to read. Where the entire consultation has been set to confidential the data from the consultation is not displayed. It is replaced by the text <code>The details of this consultation have been set as confidential</code>.<br /><br />Where individual items in the consultation have been set to confidential those items are not displayed and replaced by the text <code>Confidential item</code>.</td>
      <td style="text-align: center"><i class="fas fa-times text-danger" /></td>
    </tr>
    <tr>
      <td><code>Follow-up Actions</code></td>
      <td>A duplicate of any follow-up actions identified during the encounter entered into the <code>[actions]</code> section of the PDF document.</td>
      <td style="text-align: center"><i class="fas fa-times text-danger" /></td>
    </tr>
  </tbody>
</table>

---