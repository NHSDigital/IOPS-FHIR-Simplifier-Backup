```xml
<section>
  <title value="Contacts with professionals" />
  <code>
    <coding>
      <system value="https://fhir.nhs.uk/CodeSystem/SectionCode" />
      <code value="contacts-with-professionals" />
      <display value="Contacts with professionals" />
    </coding>
  </code>
  <text>
    <status value="additional" />
    <div xmlns="http://www.w3.org/1999/xhtml">
      <table width="100%">
        <tbody>
          <tr>
            <th>Date and time of contact</th>
            <td>9-May-2018 10:00</td>
          </tr>
          <tr>
            <th>Service</th>
            <td>Community Pharmacist Consultation Service</td>
          </tr>
          <tr>
            <th>Organisation</th>
            <td>
              <p>Name: Overtown Pharmacy</p>
              <p>Address: 1 High Street, Overtown, Leeds</p>
              <p>Postcode: LS1 9AM</p>
              <p>Telephone: 01134875516</p>
              <p>Email: overtonpharmacy118@mymail.com</p>
            </td>
          </tr>
          <tr>
            <th>Clincian</th>
            <td>
              <p>Name: Mr Eric Smith</p>
              <p>Role: Pharmacist</p>
              <p>Registration No: 2145879
            </td>
          </tr>
          <tr>
            <th>Person collecting the medication</th>
            <td>Patient</td>
          </tr>
          <tr>
            <th>Reason for service</th>
            <td>Emergency supply of medication. Patient had not ordered their prescription.</td>
          </tr>
        </tbody>
      </table>
    </div>
  </text>
  <!--Reference to Encounter resource as the source of information for this section-->
  <entry>
    <reference value="urn:uuid:adb353f9-0953-4fb4-a4ab-f0ab04a44dbc" />
  </entry>
</section>
```

---