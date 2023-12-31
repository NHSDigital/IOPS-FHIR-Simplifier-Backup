## {{page-title}}

### Publisher

``` xml
<publisher value="NHS England" />
```
### Contact

``` xml
<contact>
	<name value="NHS England" />
	<telecom>
		<system value="email" />
		<value value="interoperabilityteam@nhs.net" />
		<use value="work" />
		<rank value="1" />
	</telecom>
</contact>


```

If additional contact details SHALL be added, then the rank value SHALL be automatically increased by "1".
For example now in the above context the rank value is "1" but if additonal contact will be added then the rank value MUST be "2".

### Copyright

```xml
<copyright value="Copyright © 2023+ NHS England Licensed under the Apache License, Version 2.0 (the \&quot;License\&quot;); you may not use this file except in compliance with the License. You may obtain a copy of the License at  http://www.apache.org/licenses/LICENSE-2.0 Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an \&quot;AS IS\&quot; BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. HL7® FHIR® standard Copyright © 2011+ HL7 The HL7® FHIR® standard is used under the FHIR license. You may obtain a copy of the FHIR license at  https://www.hl7.org/fhir/license.html." />

```

---