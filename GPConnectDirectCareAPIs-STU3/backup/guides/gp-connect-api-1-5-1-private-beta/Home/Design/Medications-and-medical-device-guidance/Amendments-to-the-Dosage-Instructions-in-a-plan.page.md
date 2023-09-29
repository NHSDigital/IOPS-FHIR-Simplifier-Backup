## {{page-title}}

Where the dosage instructions of a medication/medical device plan is amended the existing authorisation/plan <strong>MUST</strong> be stopped or discontinued and a new authorisation created.

When splitting the plan due to a change in dosage the original authorisation should retain the repeat information as it was at the instant before the dosage changed. The new authorisation should contain the number of authorised issues remaining from the original plan and the number of issues at the new dosage. The new plan should reference the origianl plan using the <code class="highlighter-rouge">priorPrescription</code> element.

For example,

Consider the case where Furosemide 20mg tablets had been authorised as a repeat with 6 authorised issues with a dosage of ‘twice daily as advised’, 1 issue was made at this dosage and then the dosage was changed to ‘One to be taken each morning’. The <code class="highlighter-rouge">authoredOn</code> and <code class="highlighter-rouge">validityPeriod.start</code> dates should be retained from the original authorisation.

The original plan would contain,

<table>
  <thead>
    <tr>
      <th>element</th>
      <th>value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>MedicationRequest.id</td>
      <td>E9881EF6-EF3A-4556-9202-A437C5E31128-HD-1</td>
    </tr>
    <tr>
      <td>MedicationRequest.extension(repeatinformation).extension(numberOfRepeatsAllowed)</td>
      <td>6</td>
    </tr>
    <tr>
      <td>MedicationRequest.extension(repeatinformation).extension(numberOfRepeatsIssued)</td>
      <td>1</td>
    </tr>
    <tr>
      <td>MedicationRequest.dosageIntruction.text</td>
      <td>‘twice daily as advised’</td>
    </tr>
    <tr>
      <td>authoredOn</td>
      <td>2020-12-21T10:59:37.493+00:00</td>
    </tr>
    <tr>
      <td>validityPeriod.start</td>
      <td>2020-12-21</td>
    </tr>
  </tbody>
</table>

<p>and the new plan would contain,</p>

<table>
  <thead>
    <tr>
      <th>element</th>
      <th>value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>MedicationRequest.id</td>
      <td>E9881EF6-EF3A-4556-9202-A437C5E31128</td>
    </tr>
    <tr>
      <td>MedicationRequest.extension(repeatinformation).extension(numberOfRepeatsAllowed)</td>
      <td>5</td>
    </tr>
    <tr>
      <td>MedicationRequest.extension(repeatinformation).extension(numberOfRepeatsIssued)</td>
      <td>0</td>
    </tr>
    <tr>
      <td>MedicationRequest.dosageIntruction.text</td>
      <td>‘One to be taken each morning’</td>
    </tr>
    <tr>
      <td>MedicationRequest.priorPrescription</td>
      <td>E9881EF6-EF3A-4556-9202-A437C5E31128-HD-1</td>
    </tr>
    <tr>
      <td>authoredOn</td>
      <td>2020-12-21T10:59:37.493+00:00</td>
    </tr>
    <tr>
      <td>validityPeriod.start</td>
      <td>2020-12-21</td>
    </tr>
  </tbody>
</table>

<p>The populated resources for this example are shown below,</p>

<figure class="highlight"><pre><code class="language-json" data-lang="json"><span class="p">{</span><span class="w">
    </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Bundle"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"meta"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
        </span><span class="s2">"profile"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
            </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/GPConnect-StructuredRecord-Bundle-1"</span><span class="w">
        </span><span class="p">]</span><span class="w">
    </span><span class="p">},</span><span class="w">
    </span><span class="s2">"type"</span><span class="p">:</span><span class="w"> </span><span class="s2">"collection"</span><span class="p">,</span><span class="w">
    </span><span class="s2">"entry"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
	</span><span class="p">{</span><span class="w">
            </span><span class="s2">"resource"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"MedicationRequest"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"E9881EF6-EF3A-4556-9202-A437C5E31128-HD-1"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"meta"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"profile"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                        </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"</span><span class="w">
                    </span><span class="p">]</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"extension"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"url"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationRepeatInformation-1"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"extension"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                            </span><span class="p">{</span><span class="w">
                                </span><span class="s2">"url"</span><span class="p">:</span><span class="w"> </span><span class="s2">"numberOfRepeatPrescriptionsAllowed"</span><span class="p">,</span><span class="w">
                                </span><span class="s2">"valueUnsignedInt"</span><span class="p">:</span><span class="w"> </span><span class="mi">6</span><span class="w">
                            </span><span class="p">},</span><span class="w">
                            </span><span class="p">{</span><span class="w">
                                </span><span class="s2">"url"</span><span class="p">:</span><span class="w"> </span><span class="s2">"numberOfRepeatPrescriptionsIssued"</span><span class="p">,</span><span class="w">
                                </span><span class="s2">"valueUnsignedInt"</span><span class="p">:</span><span class="w"> </span><span class="mi">1</span><span class="w">
                            </span><span class="p">}</span><span class="w">
                        </span><span class="p">]</span><span class="w">
                    </span><span class="p">},</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"url"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"valueCodeableConcept"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                            </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                                </span><span class="p">{</span><span class="w">
                                    </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1"</span><span class="p">,</span><span class="w">
                                    </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"repeat"</span><span class="p">,</span><span class="w">
                                    </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Repeat"</span><span class="w">
                                </span><span class="p">}</span><span class="w">
                            </span><span class="p">]</span><span class="w">
                        </span><span class="p">}</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">],</span><span class="w">
                </span><span class="s2">"identifier"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://EMISWeb/A82038"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="s2">"E9881EF6-EF3A-4556-9202-A437C5E31128-HD-1"</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">],</span><span class="w">
                </span><span class="s2">"groupIdentifier"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="s2">"e9881ef6-ef3a-4556-9202-a437c5e31128-hd-1"</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"status"</span><span class="p">:</span><span class="w"> </span><span class="s2">"completed"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"intent"</span><span class="p">:</span><span class="w"> </span><span class="s2">"plan"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"medicationReference"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"reference"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Medication/F87D9962-6D02-41C7-85C7-735214FA6FC5"</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"subject"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"reference"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Patient/4DBBED7B-7A91-47DC-B99B-35CDFA970590"</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"authoredOn"</span><span class="p">:</span><span class="w"> </span><span class="s2">"2020-12-21T10:57:18.563+00:00"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"recorder"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"reference"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Practitioner/6D340A1B-BC15-4D4E-93CF-BBCB5B74DF73"</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"dosageInstruction"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"text"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Twice daily as advised"</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">],</span><span class="w">
                </span><span class="s2">"dispenseRequest"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"validityPeriod"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"start"</span><span class="p">:</span><span class="w"> </span><span class="s2">"2020-12-21"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"end"</span><span class="p">:</span><span class="w"> </span><span class="s2">"2020-12-21"</span><span class="w">
                    </span><span class="p">},</span><span class="w">
                    </span><span class="s2">"quantity"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="mi">28</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"unit"</span><span class="p">:</span><span class="w"> </span><span class="s2">"tablet"</span><span class="w">
                    </span><span class="p">},</span><span class="w">
                    </span><span class="s2">"expectedSupplyDuration"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="mi">28</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"unit"</span><span class="p">:</span><span class="w"> </span><span class="s2">"day"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"http://unitsofmeasure.org"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"d"</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">}</span><span class="w">
            </span><span class="p">}</span><span class="w">
        </span><span class="p">},</span><span class="w">
        </span><span class="p">{</span><span class="w">
            </span><span class="s2">"resource"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"MedicationRequest"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"A002B1FE-2184-4F8D-BD02-C74A813125F2"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"meta"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"profile"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                        </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"</span><span class="w">
                    </span><span class="p">]</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"extension"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"url"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"valueCodeableConcept"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                            </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                                </span><span class="p">{</span><span class="w">
                                    </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1"</span><span class="p">,</span><span class="w">
                                    </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"repeat"</span><span class="p">,</span><span class="w">
                                    </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Repeat"</span><span class="w">
                                </span><span class="p">}</span><span class="w">
                            </span><span class="p">]</span><span class="w">
                        </span><span class="p">}</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">],</span><span class="w">
                </span><span class="s2">"identifier"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://EMISWeb/A82038"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="s2">"A002B1FE-2184-4F8D-BD02-C74A813125F2"</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">],</span><span class="w">
                </span><span class="s2">"basedOn"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"reference"</span><span class="p">:</span><span class="w"> </span><span class="s2">"MedicationRequest/E9881EF6-EF3A-4556-9202-A437C5E31128-HD-1"</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">],</span><span class="w">
                </span><span class="s2">"groupIdentifier"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="s2">"e9881ef6-ef3a-4556-9202-a437c5e31128-hd-1"</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"status"</span><span class="p">:</span><span class="w"> </span><span class="s2">"completed"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"intent"</span><span class="p">:</span><span class="w"> </span><span class="s2">"order"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"medicationReference"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"reference"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Medication/F87D9962-6D02-41C7-85C7-735214FA6FC5"</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"subject"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"reference"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Patient/4DBBED7B-7A91-47DC-B99B-35CDFA970590"</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"authoredOn"</span><span class="p">:</span><span class="w"> </span><span class="s2">"2020-12-21T10:59:37.493+00:00"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"recorder"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"reference"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Practitioner/6D340A1B-BC15-4D4E-93CF-BBCB5B74DF73"</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"dosageInstruction"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"text"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Twice daily as advised"</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">],</span><span class="w">
                </span><span class="s2">"dispenseRequest"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"validityPeriod"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"start"</span><span class="p">:</span><span class="w"> </span><span class="s2">"2020-12-21"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"end"</span><span class="p">:</span><span class="w"> </span><span class="s2">"2021-01-18"</span><span class="w">
                    </span><span class="p">},</span><span class="w">
                    </span><span class="s2">"quantity"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="mi">28</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"unit"</span><span class="p">:</span><span class="w"> </span><span class="s2">"tablet"</span><span class="w">
                    </span><span class="p">},</span><span class="w">
                    </span><span class="s2">"expectedSupplyDuration"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="mi">28</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"unit"</span><span class="p">:</span><span class="w"> </span><span class="s2">"day"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"http://unitsofmeasure.org"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"d"</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">}</span><span class="w">
            </span><span class="p">}</span><span class="w">
        </span><span class="p">},</span><span class="w">
		</span><span class="p">{</span><span class="w">
            </span><span class="s2">"resource"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"MedicationRequest"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"E9881EF6-EF3A-4556-9202-A437C5E31128"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"meta"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"profile"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                        </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-MedicationRequest-1"</span><span class="w">
                    </span><span class="p">]</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"extension"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"url"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-MedicationRepeatInformation-1"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"extension"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                            </span><span class="p">{</span><span class="w">
                                </span><span class="s2">"url"</span><span class="p">:</span><span class="w"> </span><span class="s2">"numberOfRepeatPrescriptionsAllowed"</span><span class="p">,</span><span class="w">
                                </span><span class="s2">"valueUnsignedInt"</span><span class="p">:</span><span class="w"> </span><span class="mi">5</span><span class="w">
                            </span><span class="p">},</span><span class="w">
                            </span><span class="p">{</span><span class="w">
                                </span><span class="s2">"url"</span><span class="p">:</span><span class="w"> </span><span class="s2">"numberOfRepeatPrescriptionsIssued"</span><span class="p">,</span><span class="w">
                                </span><span class="s2">"valueUnsignedInt"</span><span class="p">:</span><span class="w"> </span><span class="mi">0</span><span class="w">
                            </span><span class="p">}</span><span class="w">
                        </span><span class="p">]</span><span class="w">
                    </span><span class="p">},</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"url"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/Extension-CareConnect-GPC-PrescriptionType-1"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"valueCodeableConcept"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                            </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                                </span><span class="p">{</span><span class="w">
                                    </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.nhs.uk/STU3/CodeSystem/CareConnect-PrescriptionType-1"</span><span class="p">,</span><span class="w">
                                    </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"repeat"</span><span class="p">,</span><span class="w">
                                    </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Repeat"</span><span class="w">
                                </span><span class="p">}</span><span class="w">
                            </span><span class="p">]</span><span class="w">
                        </span><span class="p">}</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">],</span><span class="w">
                </span><span class="s2">"identifier"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://EMISWeb/A82038"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="s2">"E9881EF6-EF3A-4556-9202-A437C5E31128"</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">],</span><span class="w">
                </span><span class="s2">"groupIdentifier"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="s2">"e9881ef6-ef3a-4556-9202-a437c5e31128"</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"status"</span><span class="p">:</span><span class="w"> </span><span class="s2">"active"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"intent"</span><span class="p">:</span><span class="w"> </span><span class="s2">"plan"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"medicationReference"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"reference"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Medication/F87D9962-6D02-41C7-85C7-735214FA6FC5"</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"subject"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"reference"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Patient/4DBBED7B-7A91-47DC-B99B-35CDFA970590"</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"authoredOn"</span><span class="p">:</span><span class="w"> </span><span class="s2">"2020-12-21T10:59:37.493+00:00"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"recorder"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"reference"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Practitioner/6D340A1B-BC15-4D4E-93CF-BBCB5B74DF73"</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"dosageInstruction"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                    </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"text"</span><span class="p">:</span><span class="w"> </span><span class="s2">"One To Be Taken Each Morning"</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">],</span><span class="w">
                </span><span class="s2">"dispenseRequest"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"validityPeriod"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"start"</span><span class="p">:</span><span class="w"> </span><span class="s2">"2020-12-21"</span><span class="w">
                    </span><span class="p">},</span><span class="w">
                    </span><span class="s2">"quantity"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="mi">28</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"unit"</span><span class="p">:</span><span class="w"> </span><span class="s2">"tablet"</span><span class="w">
                    </span><span class="p">},</span><span class="w">
                    </span><span class="s2">"expectedSupplyDuration"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                        </span><span class="s2">"value"</span><span class="p">:</span><span class="w"> </span><span class="mi">28</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"unit"</span><span class="p">:</span><span class="w"> </span><span class="s2">"day"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"http://unitsofmeasure.org"</span><span class="p">,</span><span class="w">
                        </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"d"</span><span class="w">
                    </span><span class="p">}</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"priorPrescription"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"reference"</span><span class="p">:</span><span class="w"> </span><span class="s2">"MedicationRequest/E9881EF6-EF3A-4556-9202-A437C5E31128-HD-1"</span><span class="w">
                </span><span class="p">}</span><span class="w">
            </span><span class="p">}</span><span class="w">
        </span><span class="p">},</span><span class="w">
		        </span><span class="p">{</span><span class="w">
            </span><span class="s2">"resource"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                </span><span class="s2">"resourceType"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Medication"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"id"</span><span class="p">:</span><span class="w"> </span><span class="s2">"F87D9962-6D02-41C7-85C7-735214FA6FC5"</span><span class="p">,</span><span class="w">
                </span><span class="s2">"meta"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"profile"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                        </span><span class="s2">"https://fhir.nhs.uk/STU3/StructureDefinition/CareConnect-GPC-Medication-1"</span><span class="w">
                    </span><span class="p">]</span><span class="w">
                </span><span class="p">},</span><span class="w">
                </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="p">{</span><span class="w">
                    </span><span class="s2">"coding"</span><span class="p">:</span><span class="w"> </span><span class="p">[</span><span class="w">
                        </span><span class="p">{</span><span class="w">
                            </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"https://fhir.hl7.org.uk/Id/emis-drug-codes"</span><span class="p">,</span><span class="w">
                            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"FUTA17675NEMIS"</span><span class="p">,</span><span class="w">
                            </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Furosemide 20mg tablets"</span><span class="p">,</span><span class="w">
                            </span><span class="s2">"userSelected"</span><span class="p">:</span><span class="w"> </span><span class="kc">true</span><span class="w">
                        </span><span class="p">},</span><span class="w">
                        </span><span class="p">{</span><span class="w">
                            </span><span class="s2">"system"</span><span class="p">:</span><span class="w"> </span><span class="s2">"http://snomed.info/sct"</span><span class="p">,</span><span class="w">
                            </span><span class="s2">"code"</span><span class="p">:</span><span class="w"> </span><span class="s2">"317971007"</span><span class="p">,</span><span class="w">
                            </span><span class="s2">"display"</span><span class="p">:</span><span class="w"> </span><span class="s2">"Furosemide 20mg tablets"</span><span class="w">
                        </span><span class="p">}</span><span class="w">
                    </span><span class="p">]</span><span class="w">
                </span><span class="p">}</span><span class="w">
            </span><span class="p">}</span><span class="w">
        </span><span class="p">}</span><span class="w">
    </span><span class="p">]</span><span class="w">
</span><span class="p">}</span></code></pre></figure>

