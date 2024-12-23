## {{page-title}}

### Allergic to Paracetamol
An example using an Actual Medicinal Product (AMP).

```html
<section>
    <title value="Allergies and adverse reactions"/>
    <code>
        <coding>
            <system value="http://snomed.info/sct"/>
            <code value="886921000000105"/>
            <display value="Allergies and adverse reactions"/>
        </coding>
    </code>
    <text>
        <status value="additional"/>
        <div xmlns="http://www.w3.org/1999/xhtml">
            <table width="100%">
                <tbody>
                    <tr>
                        <th>Causative agent</th>
                        <td>Paracetamol 500mg tablets (A A H Pharmaceuticals Ltd)</td>
                    </tr>
                    <tr>
                        <th>Description of reaction</th>
                        <td>sample adverse event</td>
                    </tr>
                    <tr>
                        <th>Type of reaction</th>
                        <td>Allergy</td>
                    </tr>
                    <tr>
                        <th>Severity</th>
                        <td>Mild</td>
                    </tr>
                    <tr>
                        <th>Certainty</th>
                        <td>Confirmed</td>
                    </tr>
                    <tr>
                        <th>Date recorded</th>
                        <td>31 May 2020 21:53</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </text>
    <entry>
        <reference value="urn:uuid:a9f3d7fc-4129-4f55-8757-c1b170ad6967"/>
    </entry>
</section>
```

### No known drug allergy
```html
<section>
    <title value="Allergies and Adverse Reactions"/>
    <code>
        <coding>
            <system value="http://snomed.info/sct"/>
            <code value="886921000000105"/>
            <display value="Allergies and adverse reactions"/>
        </coding>
    </code>
    <text>
        <status value="additional"/>
        <div xmlns="http://www.w3.org/1999/xhtml">
            <table width="100%">
                <tbody>
                    <tr>
                        <th>Causative agent</th>
                        <td>No known drug allergy</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </text>
    <!--Reference to Allergies List as the source of information for this section-->
    <entry>
        <reference value="urn:uuid:82d40ab3-6304-4620-8ba5-95234631dca6"/>
    </entry>
							</section>
```

---