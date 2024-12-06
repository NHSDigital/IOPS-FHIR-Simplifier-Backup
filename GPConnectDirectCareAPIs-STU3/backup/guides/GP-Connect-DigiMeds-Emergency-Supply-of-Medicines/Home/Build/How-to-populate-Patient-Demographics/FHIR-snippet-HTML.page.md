## {{page-title}}


```xml
<section>
  <title value="Patient Demographics" />
  <code>
    <coding>
      <system value="http://snomed.info/sct" />
      <code value="886731000000109" />
      <display value="Patient demographics" />
    </coding>
  </code>
  <text>
    <status value="additional" />
    <div xmlns="http://www.w3.org/1999/xhtml">
      <table width="100%">
        <tbody>
          <tr>
            <th>Patient</th>
            <td>
              <p>Prefix: Mr</p>
              <p>Given Name: William</p>
              <p>Family Name: Smith</p>
            </td>
          </tr>
          <tr>
            <th>Date of birth</th>
            <td>4 February 1956</td>
          </tr>
          <tr>
            <th>Gender</th>
            <td>Male</td>
          </tr>
          <tr>
            <th>NHS number</th>
            <td>2378954317</td>
          </tr>
          <tr>
            <th>Patient address</th>
            <td>
              <p>Address Line: 14, Sunny Mews, Overtown,</p>
              <p>City: Leeds</p>
              <p>Post Code: LS17 4NK</p>
            </td>
          </tr>
          <tr>
            <th>Patient telephone number</th>
            <td>
              <p>Home: 01135540935</p>
              <p>Mobile: 07823123456</p>
            </td>
          </tr>
          <tr>
            <th>Relevant contacts</th>
            <td>Name: June Smith <p>Relationship: Next of kin</p>
              <p>Contact details: Tel.
              01132789365</p>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </text>
  <!--reference to further information carried in the patient resource-->
  <entry>
    <reference value="urn:uuid:1e2b5223-1cd8-43ff-8a67-55dec3edb9b0" />
  </entry>
</section>
```