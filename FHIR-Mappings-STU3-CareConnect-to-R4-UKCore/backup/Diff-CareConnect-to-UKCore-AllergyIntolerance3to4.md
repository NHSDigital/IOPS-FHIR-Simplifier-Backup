<h1 class="code-line" data-line-start=0 data-line-end=1><a id="FHIR_Profile_Diff_0"></a>AllergyIntolerance Profile Diff</h1>
<p class="has-line-data" data-line-start="1" data-line-end="2"><strong>Base profile:</strong> AllergyIntolerance</p>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>Lefthand Profile</th>
         <th>Version</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>CareConnect-AllergyIntolerance-1</td>
         <td>3.0.1</td>
      </tr>
   </tbody>
</table>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>Righthand Profile</th>
         <th>Version</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>UKCoreAllergyIntolerance</td>
         <td>4.0.1</td>
      </tr>
   </tbody>
</table>
<hr>
<h1 class="code-line" data-line-start=10 data-line-end=11><a id="Element_level_diff_10"></a>Element level diff</h1>
<p class="has-line-data" data-line-start="11" data-line-end="12"><strong>Profiles:</strong></p>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody></tbody>
</table>
<p class="has-line-data" data-line-start="14" data-line-end="15"><strong>Diff:</strong></p>
<pre><code class="has-line-data" data-line-start="16" data-line-end="72" class="language-diff"> AllergyIntolerance.extension  
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.extension:encounter  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.extension:allergyEnd  </span>
<span class="hljs-addition", style="color:green">+AllergyIntolerance.extension:allergyIntoleranceEnd  </span>
 AllergyIntolerance.extension:evidence  
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.identifier.system  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.identifier.value  </span>
 AllergyIntolerance.identifier.assigner  
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.verificationStatus  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.code.coding  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.code.coding:snomedCT  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.code.coding:snomedCT.extension  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.code.coding:snomedCT.extension:snomedCTDescriptionID  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.code.coding:snomedCT.system  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.code.coding:snomedCT.code  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.code.coding:snomedCT.display  </span>
<span class="hljs-addition", style="color:green">+AllergyIntolerance.code  </span>
 AllergyIntolerance.patient  
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.onset[x]  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.assertedDate  </span>
<span class="hljs-addition", style="color:green">+AllergyIntolerance.patient.identifier.assigner  </span>
<span class="hljs-addition", style="color:green">+AllergyIntolerance.encounter  </span>
<span class="hljs-addition", style="color:green">+AllergyIntolerance.encounter.identifier.assigner  </span>
 AllergyIntolerance.recorder  
<span class="hljs-addition", style="color:green">+AllergyIntolerance.recorder.identifier.assigner  </span>
 AllergyIntolerance.asserter  
<span class="hljs-addition", style="color:green">+AllergyIntolerance.asserter.identifier.assigner  </span>
 AllergyIntolerance.note.author[x]  
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.substance.coding  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.substance.coding:snomedCT  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.substance.coding:snomedCT.extension  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.substance.coding:snomedCT.extension:snomedCTDescriptionID  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.substance.coding:snomedCT.system  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.substance.coding:snomedCT.code  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.substance.coding:snomedCT.display  </span>
<span class="hljs-addition", style="color:green">+AllergyIntolerance.reaction.substance  </span>
 AllergyIntolerance.reaction.manifestation  
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.manifestation.coding  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.manifestation.coding:snomedCT  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.manifestation.coding:snomedCT.extension  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.manifestation.coding:snomedCT.extension:snomedCTDescriptionID  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.manifestation.coding:snomedCT.system  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.manifestation.coding:snomedCT.code  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.manifestation.coding:snomedCT.display  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.severity  </span>
 AllergyIntolerance.reaction.exposureRoute  
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.exposureRoute.coding  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.exposureRoute.coding:snomedCT  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.exposureRoute.coding:snomedCT.extension  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.exposureRoute.coding:snomedCT.extension:snomedCTDescriptionID  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.exposureRoute.coding:snomedCT.system  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.exposureRoute.coding:snomedCT.code  </span>
<span class="hljs-deletion", style="color:red">-AllergyIntolerance.reaction.exposureRoute.coding:snomedCT.display  </span>
 AllergyIntolerance.reaction.note.author[x]  

</code></pre>
<hr>
<h1 class="code-line" data-line-start=73 data-line-end=74><a id="Component_level_diff_73"></a>Component level diff</h1>
<h2 class="code-line" data-line-start=75 data-line-end=76><a id="Element_AllergyIntoleranceextension_75"></a>Element: <em>AllergyIntolerance.extension</em></h2>
<h3 class="code-line" data-line-start=77 data-line-end=78><a id="Component_min_77"></a>Component: <em>min</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Not defined</td>
         <td>0</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=84 data-line-end=85><a id="Base_84"></a>Base</h4>
<p class="has-line-data" data-line-start="85" data-line-end="86">“min” == 0</p>
<h2 class="code-line" data-line-start=89 data-line-end=90><a id="Element_AllergyIntoleranceextensionevidence_89"></a>Element: <em>AllergyIntolerance.extension:evidence</em></h2>
<h3 class="code-line" data-line-start=91 data-line-end=92><a id="Component_min_91"></a>Component: <em>min</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Not defined</td>
         <td>0</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=98 data-line-end=99><a id="Base_98"></a>Base</h4>
<p class="has-line-data" data-line-start="99" data-line-end="100">“min” == 0</p>
<h2 class="code-line" data-line-start=103 data-line-end=104><a id="Element_AllergyIntoleranceidentifierassigner_103"></a>Element: <em>AllergyIntolerance.identifier.assigner</em></h2>
<h3 class="code-line" data-line-start=105 data-line-end=106><a id="Component_type_105"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>See diff</td>
         <td>See diff</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=111 data-line-end=112><a id="Diff_111"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="113" data-line-end="124" class="language-diff"> [  
   {  
     "code": "Reference",  
<span class="hljs-deletion", style="color:red">-    "targetProfile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Organization-1"  </span>
<span class="hljs-addition", style="color:green">+    "targetProfile": [  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Organization"  </span>
<span class="hljs-addition", style="color:green">+    ]  </span>
   }  
 ]  
  
</code></pre>
<h4 class="code-line" data-line-start=126 data-line-end=127><a id="Base_126"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="128" data-line-end="135" class="language-json">[
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Reference"</span></span>,
    "<span class="hljs-attribute">targetProfile</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/Organization"</span>
  </span>}
]
</code></pre>
<h2 class="code-line" data-line-start=138 data-line-end=139><a id="Element_AllergyIntolerancepatient_138"></a>Element: <em>AllergyIntolerance.patient</em></h2>
<h3 class="code-line" data-line-start=140 data-line-end=141><a id="Component_type_140"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>See diff</td>
         <td>See diff</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=146 data-line-end=147><a id="Diff_146"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="148" data-line-end="159" class="language-diff"> [  
   {  
     "code": "Reference",  
<span class="hljs-deletion", style="color:red">-    "targetProfile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1"  </span>
<span class="hljs-addition", style="color:green">+    "targetProfile": [  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Patient"  </span>
<span class="hljs-addition", style="color:green">+    ]  </span>
   }  
 ]  
  
</code></pre>
<h4 class="code-line" data-line-start=161 data-line-end=162><a id="Base_161"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="163" data-line-end="170" class="language-json">[
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Reference"</span></span>,
    "<span class="hljs-attribute">targetProfile</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/Patient"</span>
  </span>}
]
</code></pre>
<h2 class="code-line" data-line-start=173 data-line-end=174><a id="Element_AllergyIntolerancerecorder_173"></a>Element: <em>AllergyIntolerance.recorder</em></h2>
<h3 class="code-line" data-line-start=175 data-line-end=176><a id="Component_type_175"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>See diff</td>
         <td>See diff</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=181 data-line-end=182><a id="Diff_181"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="183" data-line-end="201" class="language-diff"> [  
   {  
     "code": "Reference",  
<span class="hljs-deletion", style="color:red">-    "targetProfile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1"  </span>
<span class="hljs-deletion", style="color:red">-  },  </span>
<span class="hljs-deletion", style="color:red">-  {  </span>
<span class="hljs-deletion", style="color:red">-    "code": "Reference",  </span>
<span class="hljs-deletion", style="color:red">-    "targetProfile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1"  </span>
<span class="hljs-addition", style="color:green">+    "targetProfile": [  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Practitioner",  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-PractitionerRole",  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Patient",  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-RelatedPerson"  </span>
<span class="hljs-addition", style="color:green">+    ]  </span>
   }  
 ]  
  
</code></pre>
<h4 class="code-line" data-line-start=203 data-line-end=204><a id="Base_203"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="205" data-line-end="216" class="language-json">[
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Reference"</span></span>,
    "<span class="hljs-attribute">targetProfile</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/Practitioner"</span>
  </span>},
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Reference"</span></span>,
    "<span class="hljs-attribute">targetProfile</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/Patient"</span>
  </span>}
]
</code></pre>
<h2 class="code-line" data-line-start=219 data-line-end=220><a id="Element_AllergyIntoleranceasserter_219"></a>Element: <em>AllergyIntolerance.asserter</em></h2>
<h3 class="code-line" data-line-start=221 data-line-end=222><a id="Component_type_221"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>See diff</td>
         <td>See diff</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=227 data-line-end=228><a id="Diff_227"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="229" data-line-end="251" class="language-diff"> [  
   {  
     "code": "Reference",  
<span class="hljs-deletion", style="color:red">-    "targetProfile": "http://hl7.org/fhir/StructureDefinition/RelatedPerson"  </span>
<span class="hljs-deletion", style="color:red">-  },  </span>
<span class="hljs-deletion", style="color:red">-  {  </span>
<span class="hljs-deletion", style="color:red">-    "code": "Reference",  </span>
<span class="hljs-deletion", style="color:red">-    "targetProfile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1"  </span>
<span class="hljs-deletion", style="color:red">-  },  </span>
<span class="hljs-deletion", style="color:red">-  {  </span>
<span class="hljs-deletion", style="color:red">-    "code": "Reference",  </span>
<span class="hljs-deletion", style="color:red">-    "targetProfile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1"  </span>
<span class="hljs-addition", style="color:green">+    "targetProfile": [  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Patient",  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-RelatedPerson",  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Practitioner",  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-PractitionerRole"  </span>
<span class="hljs-addition", style="color:green">+    ]  </span>
   }  
 ]  
  
</code></pre>
<h4 class="code-line" data-line-start=253 data-line-end=254><a id="Base_253"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="255" data-line-end="270" class="language-json">[
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Reference"</span></span>,
    "<span class="hljs-attribute">targetProfile</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/Patient"</span>
  </span>},
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Reference"</span></span>,
    "<span class="hljs-attribute">targetProfile</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/RelatedPerson"</span>
  </span>},
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Reference"</span></span>,
    "<span class="hljs-attribute">targetProfile</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/Practitioner"</span>
  </span>}
]
</code></pre>
<h2 class="code-line" data-line-start=273 data-line-end=274><a id="Element_AllergyIntolerancenoteauthorx_273"></a>Element: <em>AllergyIntolerance.note.author[x]</em></h2>
<h3 class="code-line" data-line-start=275 data-line-end=276><a id="Component_type_275"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>See diff</td>
         <td>See diff</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=281 data-line-end=282><a id="Diff_281"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="283" data-line-end="308" class="language-diff"> [  
   {  
     "code": "Reference",  
<span class="hljs-deletion", style="color:red">-    "targetProfile": "http://hl7.org/fhir/StructureDefinition/RelatedPerson"  </span>
<span class="hljs-addition", style="color:green">+    "targetProfile": [  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Practitioner",  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Patient",  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-RelatedPerson",  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Organization"  </span>
<span class="hljs-addition", style="color:green">+    ]  </span>
   },  
   {  
     "code": "string"  
<span class="hljs-deletion", style="color:red">-  },  </span>
<span class="hljs-deletion", style="color:red">-  {  </span>
<span class="hljs-deletion", style="color:red">-    "code": "Reference",  </span>
<span class="hljs-deletion", style="color:red">-    "targetProfile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1"  </span>
<span class="hljs-deletion", style="color:red">-  },  </span>
<span class="hljs-deletion", style="color:red">-  {  </span>
<span class="hljs-deletion", style="color:red">-    "code": "Reference",  </span>
<span class="hljs-deletion", style="color:red">-    "targetProfile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1"  </span>
   }  
 ]  
  
</code></pre>
<h4 class="code-line" data-line-start=310 data-line-end=311><a id="Base_310"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="312" data-line-end="330" class="language-json">[
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Reference"</span></span>,
    "<span class="hljs-attribute">targetProfile</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/Practitioner"</span>
  </span>},
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Reference"</span></span>,
    "<span class="hljs-attribute">targetProfile</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/Patient"</span>
  </span>},
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Reference"</span></span>,
    "<span class="hljs-attribute">targetProfile</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/RelatedPerson"</span>
  </span>},
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"string"</span>
  </span>}
]
</code></pre>
<h2 class="code-line" data-line-start=333 data-line-end=334><a id="Element_AllergyIntolerancereactionmanifestation_333"></a>Element: <em>AllergyIntolerance.reaction.manifestation</em></h2>
<h3 class="code-line" data-line-start=335 data-line-end=336><a id="Component_binding_335"></a>Component: <em>binding</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>See diff</td>
         <td>See diff</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=341 data-line-end=342><a id="Diff_341"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="343" data-line-end="358" class="language-diff"> {  
<span class="hljs-deletion", style="color:red">-  "extension": [  </span>
<span class="hljs-deletion", style="color:red">-    {  </span>
<span class="hljs-deletion", style="color:red">-      "url": "http://hl7.org/fhir/StructureDefinition/elementdefinition-bindingName",  </span>
<span class="hljs-deletion", style="color:red">-      "valueString": "Manifestation"  </span>
<span class="hljs-deletion", style="color:red">-    }  </span>
<span class="hljs-deletion", style="color:red">-  ],  </span>
   "strength": "extensible",  
<span class="hljs-deletion", style="color:red">-  "valueSetReference": {  </span>
<span class="hljs-deletion", style="color:red">-    "reference": "https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-AllergyManifestation-1"  </span>
<span class="hljs-deletion", style="color:red">-  }  </span>
<span class="hljs-addition", style="color:green">+  "valueSet": "https://fhir.simplifier.net/HL7FHIRUKCoreR4/ValueSet/UKCore-AllergyManifestation"  </span>
 }  
  
</code></pre>
<h4 class="code-line" data-line-start=360 data-line-end=361><a id="Base_360"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="362" data-line-end="376" class="language-json">{
  "<span class="hljs-attribute">description</span>": <span class="hljs-value"><span class="hljs-string">"Clinical symptoms and/or signs that are observed or associated with an Adverse Reaction Event."</span></span>,
  "<span class="hljs-attribute">extension</span>": <span class="hljs-value">[
    {
      "<span class="hljs-attribute">url</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/elementdefinition-bindingName"</span></span>,
      "<span class="hljs-attribute">valueString</span>": <span class="hljs-value"><span class="hljs-string">"Manifestation"</span>
    </span>}
  ]</span>,
  "<span class="hljs-attribute">strength</span>": <span class="hljs-value"><span class="hljs-string">"example"</span></span>,
  "<span class="hljs-attribute">valueSetReference</span>": <span class="hljs-value">{
    "<span class="hljs-attribute">reference</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/ValueSet/clinical-findings"</span>
  </span>}
</span>}
</code></pre>
<h2 class="code-line" data-line-start=379 data-line-end=380><a id="Element_AllergyIntolerancereactionexposureRoute_379"></a>Element: <em>AllergyIntolerance.reaction.exposureRoute</em></h2>
<h3 class="code-line" data-line-start=381 data-line-end=382><a id="Component_binding_381"></a>Component: <em>binding</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>See diff</td>
         <td>See diff</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=387 data-line-end=388><a id="Diff_387"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="389" data-line-end="405" class="language-diff"> {  
<span class="hljs-deletion", style="color:red">-  "extension": [  </span>
<span class="hljs-deletion", style="color:red">-    {  </span>
<span class="hljs-deletion", style="color:red">-      "url": "http://hl7.org/fhir/StructureDefinition/elementdefinition-bindingName",  </span>
<span class="hljs-deletion", style="color:red">-      "valueString": "RouteOfAdministration"  </span>
<span class="hljs-deletion", style="color:red">-    }  </span>
<span class="hljs-deletion", style="color:red">-  ],  </span>
<span class="hljs-deletion", style="color:red">-  "strength": "example",  </span>
<span class="hljs-deletion", style="color:red">-  "valueSetReference": {  </span>
<span class="hljs-deletion", style="color:red">-    "reference": "https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-AllergyExposureRoute-1"  </span>
<span class="hljs-deletion", style="color:red">-  }  </span>
<span class="hljs-addition", style="color:green">+  "strength": "extensible",  </span>
<span class="hljs-addition", style="color:green">+  "valueSet": "https://fhir.simplifier.net/HL7FHIRUKCoreR4/ValueSet/UKCore-SubstanceOrProductAdministrationRoute"  </span>
 }  
  
</code></pre>
<h4 class="code-line" data-line-start=407 data-line-end=408><a id="Base_407"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="409" data-line-end="423" class="language-json">{
  "<span class="hljs-attribute">description</span>": <span class="hljs-value"><span class="hljs-string">"A coded concept describing the route or physiological path of administration of a therapeutic agent into or onto the body of a subject."</span></span>,
  "<span class="hljs-attribute">extension</span>": <span class="hljs-value">[
    {
      "<span class="hljs-attribute">url</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/elementdefinition-bindingName"</span></span>,
      "<span class="hljs-attribute">valueString</span>": <span class="hljs-value"><span class="hljs-string">"RouteOfAdministration"</span>
    </span>}
  ]</span>,
  "<span class="hljs-attribute">strength</span>": <span class="hljs-value"><span class="hljs-string">"example"</span></span>,
  "<span class="hljs-attribute">valueSetReference</span>": <span class="hljs-value">{
    "<span class="hljs-attribute">reference</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/ValueSet/route-codes"</span>
  </span>}
</span>}
</code></pre>
<h2 class="code-line" data-line-start=426 data-line-end=427><a id="Element_AllergyIntolerancereactionnoteauthorx_426"></a>Element: <em>AllergyIntolerance.reaction.note.author[x]</em></h2>
<h3 class="code-line" data-line-start=428 data-line-end=429><a id="Component_type_428"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>See diff</td>
         <td>See diff</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=434 data-line-end=435><a id="Diff_434"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="436" data-line-end="461" class="language-diff"> [  
   {  
     "code": "Reference",  
<span class="hljs-deletion", style="color:red">-    "targetProfile": "http://hl7.org/fhir/StructureDefinition/RelatedPerson"  </span>
<span class="hljs-addition", style="color:green">+    "targetProfile": [  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Practitioner",  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Patient",  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-RelatedPerson",  </span>
<span class="hljs-addition", style="color:green">+      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Organization"  </span>
<span class="hljs-addition", style="color:green">+    ]  </span>
   },  
   {  
     "code": "string"  
<span class="hljs-deletion", style="color:red">-  },  </span>
<span class="hljs-deletion", style="color:red">-  {  </span>
<span class="hljs-deletion", style="color:red">-    "code": "Reference",  </span>
<span class="hljs-deletion", style="color:red">-    "targetProfile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Patient-1"  </span>
<span class="hljs-deletion", style="color:red">-  },  </span>
<span class="hljs-deletion", style="color:red">-  {  </span>
<span class="hljs-deletion", style="color:red">-    "code": "Reference",  </span>
<span class="hljs-deletion", style="color:red">-    "targetProfile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/CareConnect-Practitioner-1"  </span>
   }  
 ]  
  
</code></pre>
<h4 class="code-line" data-line-start=463 data-line-end=464><a id="Base_463"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="465" data-line-end="483" class="language-json">[
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Reference"</span></span>,
    "<span class="hljs-attribute">targetProfile</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/Practitioner"</span>
  </span>},
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Reference"</span></span>,
    "<span class="hljs-attribute">targetProfile</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/Patient"</span>
  </span>},
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Reference"</span></span>,
    "<span class="hljs-attribute">targetProfile</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/RelatedPerson"</span>
  </span>},
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"string"</span>
  </span>}
]
</code></pre>
<h2 class="code-line" data-line-start=486 data-line-end=487><a id="Element_AllergyIntoleranceextensionencounter_486"></a>Element: <em>AllergyIntolerance.extension:encounter</em></h2>
<h3 class="code-line" data-line-start=488 data-line-end=489><a id="Component_type_488"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=494 data-line-end=495><a id="Diff_494"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="496" data-line-end="503" class="language-diff">[
  {
    "code": "Extension",
    "profile": "http://hl7.org/fhir/StructureDefinition/encounter-associatedEncounter"
  }
]  
</code></pre>
<h4 class="code-line" data-line-start=505 data-line-end=506><a id="Base_505"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="507" data-line-end="513" class="language-json">[
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Extension"</span>
  </span>}
]
</code></pre>
<h2 class="code-line" data-line-start=516 data-line-end=517><a id="Element_AllergyIntoleranceextensionallergyEnd_516"></a>Element: <em>AllergyIntolerance.extension:allergyEnd</em></h2>
<h3 class="code-line" data-line-start=518 data-line-end=519><a id="Component_type_518"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=524 data-line-end=525><a id="Diff_524"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="526" data-line-end="533" class="language-diff">[
  {
    "code": "Extension",
    "profile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-CareConnect-AllergyIntoleranceEnd-1"
  }
]  
</code></pre>
<h4 class="code-line" data-line-start=535 data-line-end=536><a id="Base_535"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="537" data-line-end="543" class="language-json">[
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Extension"</span>
  </span>}
]
</code></pre>
<h2 class="code-line" data-line-start=546 data-line-end=547><a id="Element_AllergyIntoleranceidentifiersystem_546"></a>Element: <em>AllergyIntolerance.identifier.system</em></h2>
<h3 class="code-line" data-line-start=548 data-line-end=549><a id="Component_min_548"></a>Component: <em>min</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=555 data-line-end=556><a id="Base_555"></a>Base</h4>
<p class="has-line-data" data-line-start="556" data-line-end="557">“min” == 0</p>
<h2 class="code-line" data-line-start=560 data-line-end=561><a id="Element_AllergyIntoleranceidentifiervalue_560"></a>Element: <em>AllergyIntolerance.identifier.value</em></h2>
<h3 class="code-line" data-line-start=562 data-line-end=563><a id="Component_min_562"></a>Component: <em>min</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=569 data-line-end=570><a id="Base_569"></a>Base</h4>
<p class="has-line-data" data-line-start="570" data-line-end="571">“min” == 0</p>
<h2 class="code-line" data-line-start=574 data-line-end=575><a id="Element_AllergyIntoleranceverificationStatus_574"></a>Element: <em>AllergyIntolerance.verificationStatus</em></h2>
<h3 class="code-line" data-line-start=576 data-line-end=577><a id="Component_binding_576"></a>Component: <em>binding</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=582 data-line-end=583><a id="Diff_582"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="584" data-line-end="597" class="language-diff">{
  "extension": [
    {
      "url": "http://hl7.org/fhir/StructureDefinition/elementdefinition-bindingName",
      "valueString": "AllergyIntoleranceVerificationStatus"
    }
  ],
  "strength": "required",
  "valueSetReference": {
    "reference": "https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-AllergyVerificationStatus-1"
  }
}  
</code></pre>
<h4 class="code-line" data-line-start=599 data-line-end=600><a id="Base_599"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="601" data-line-end="615" class="language-json">{
  "<span class="hljs-attribute">description</span>": <span class="hljs-value"><span class="hljs-string">"Assertion about certainty associated with a propensity, or potential risk, of a reaction to the identified substance."</span></span>,
  "<span class="hljs-attribute">extension</span>": <span class="hljs-value">[
    {
      "<span class="hljs-attribute">url</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/elementdefinition-bindingName"</span></span>,
      "<span class="hljs-attribute">valueString</span>": <span class="hljs-value"><span class="hljs-string">"AllergyIntoleranceVerificationStatus"</span>
    </span>}
  ]</span>,
  "<span class="hljs-attribute">strength</span>": <span class="hljs-value"><span class="hljs-string">"required"</span></span>,
  "<span class="hljs-attribute">valueSetReference</span>": <span class="hljs-value">{
    "<span class="hljs-attribute">reference</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/ValueSet/allergy-verification-status"</span>
  </span>}
</span>}
</code></pre>
<h2 class="code-line" data-line-start=618 data-line-end=619><a id="Element_AllergyIntolerancecodecoding_618"></a>Element: <em>AllergyIntolerance.code.coding</em></h2>
<h3 class="code-line" data-line-start=620 data-line-end=621><a id="Component_slicing_620"></a>Component: <em>slicing</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=626 data-line-end=627><a id="Diff_626"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="628" data-line-end="638" class="language-diff">{
  "discriminator": [
    {
      "path": "system",
      "type": "value"
    }
  ],
  "rules": "open"
}  
</code></pre>
<h4 class="code-line" data-line-start=640 data-line-end=641><a id="Base_640"></a>Base</h4>
<p class="has-line-data" data-line-start="641" data-line-end="642">“slicing” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=645 data-line-end=646><a id="Element_AllergyIntolerancecodecodingsnomedCT_645"></a>Element: <em>AllergyIntolerance.code.coding:snomedCT</em></h2>
<h3 class="code-line" data-line-start=647 data-line-end=648><a id="Component_binding_647"></a>Component: <em>binding</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=653 data-line-end=654><a id="Diff_653"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="655" data-line-end="663" class="language-diff">{
  "description": "A code from the SNOMED Clinical Terminology UK or a code from the v3 Code System NullFlavor specifying why a valid value is not present.",
  "strength": "example",
  "valueSetReference": {
    "reference": "https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-AllergyCode-1"
  }
}  
</code></pre>
<h4 class="code-line" data-line-start=665 data-line-end=666><a id="Base_665"></a>Base</h4>
<p class="has-line-data" data-line-start="666" data-line-end="667">“binding” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=670 data-line-end=671><a id="Element_AllergyIntolerancecodecodingsnomedCTextension_670"></a>Element: <em>AllergyIntolerance.code.coding:snomedCT.extension</em></h2>
<h3 class="code-line" data-line-start=672 data-line-end=673><a id="Component_slicing_672"></a>Component: <em>slicing</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=678 data-line-end=679><a id="Diff_678"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="680" data-line-end="690" class="language-diff">{
  "discriminator": [
    {
      "path": "url",
      "type": "value"
    }
  ],
  "rules": "open"
}  
</code></pre>
<h4 class="code-line" data-line-start=692 data-line-end=693><a id="Base_692"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="694" data-line-end="705" class="language-json">{
  "<span class="hljs-attribute">description</span>": <span class="hljs-value"><span class="hljs-string">"Extensions are always sliced by (at least) url"</span></span>,
  "<span class="hljs-attribute">discriminator</span>": <span class="hljs-value">[
    {
      "<span class="hljs-attribute">path</span>": <span class="hljs-value"><span class="hljs-string">"url"</span></span>,
      "<span class="hljs-attribute">type</span>": <span class="hljs-value"><span class="hljs-string">"value"</span>
    </span>}
  ]</span>,
  "<span class="hljs-attribute">rules</span>": <span class="hljs-value"><span class="hljs-string">"open"</span>
</span>}
</code></pre>
<h2 class="code-line" data-line-start=708 data-line-end=709><a id="Element_AllergyIntolerancecodecodingsnomedCTextensionsnomedCTDescriptionID_708"></a>Element: <em>AllergyIntolerance.code.coding:snomedCT.extension:snomedCTDescriptionID</em></h2>
<h3 class="code-line" data-line-start=710 data-line-end=711><a id="Component_type_710"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=716 data-line-end=717><a id="Diff_716"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="718" data-line-end="725" class="language-diff">[
  {
    "code": "Extension",
    "profile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid"
  }
]  
</code></pre>
<h4 class="code-line" data-line-start=727 data-line-end=728><a id="Base_727"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="729" data-line-end="735" class="language-json">[
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Extension"</span>
  </span>}
]
</code></pre>
<h2 class="code-line" data-line-start=738 data-line-end=739><a id="Element_AllergyIntolerancecodecodingsnomedCTsystem_738"></a>Element: <em>AllergyIntolerance.code.coding:snomedCT.system</em></h2>
<h3 class="code-line" data-line-start=740 data-line-end=741><a id="Component_min_740"></a>Component: <em>min</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=747 data-line-end=748><a id="Base_747"></a>Base</h4>
<p class="has-line-data" data-line-start="748" data-line-end="749">“min” == 0</p>
<h2 class="code-line" data-line-start=752 data-line-end=753><a id="Element_AllergyIntolerancecodecodingsnomedCTcode_752"></a>Element: <em>AllergyIntolerance.code.coding:snomedCT.code</em></h2>
<h3 class="code-line" data-line-start=754 data-line-end=755><a id="Component_min_754"></a>Component: <em>min</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=761 data-line-end=762><a id="Base_761"></a>Base</h4>
<p class="has-line-data" data-line-start="762" data-line-end="763">“min” == 0</p>
<h2 class="code-line" data-line-start=766 data-line-end=767><a id="Element_AllergyIntolerancecodecodingsnomedCTdisplay_766"></a>Element: <em>AllergyIntolerance.code.coding:snomedCT.display</em></h2>
<h3 class="code-line" data-line-start=768 data-line-end=769><a id="Component_min_768"></a>Component: <em>min</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=775 data-line-end=776><a id="Base_775"></a>Base</h4>
<p class="has-line-data" data-line-start="776" data-line-end="777">“min” == 0</p>
<h2 class="code-line" data-line-start=780 data-line-end=781><a id="Element_AllergyIntoleranceonsetx_780"></a>Element: <em>AllergyIntolerance.onset[x]</em></h2>
<h3 class="code-line" data-line-start=782 data-line-end=783><a id="Component_mustSupport_782"></a>Component: <em>mustSupport</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>True</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=789 data-line-end=790><a id="Base_789"></a>Base</h4>
<p class="has-line-data" data-line-start="790" data-line-end="791">“mustSupport” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=794 data-line-end=795><a id="Element_AllergyIntoleranceassertedDate_794"></a>Element: <em>AllergyIntolerance.assertedDate</em></h2>
<h3 class="code-line" data-line-start=796 data-line-end=797><a id="Component_min_796"></a>Component: <em>min</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=803 data-line-end=804><a id="Base_803"></a>Base</h4>
<p class="has-line-data" data-line-start="804" data-line-end="805">“min” == 0</p>
<h2 class="code-line" data-line-start=808 data-line-end=809><a id="Element_AllergyIntolerancereactionsubstancecoding_808"></a>Element: <em>AllergyIntolerance.reaction.substance.coding</em></h2>
<h3 class="code-line" data-line-start=810 data-line-end=811><a id="Component_slicing_810"></a>Component: <em>slicing</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=816 data-line-end=817><a id="Diff_816"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="818" data-line-end="829" class="language-diff">{
  "discriminator": [
    {
      "path": "system",
      "type": "value"
    }
  ],
  "ordered": false,
  "rules": "open"
}  
</code></pre>
<h4 class="code-line" data-line-start=831 data-line-end=832><a id="Base_831"></a>Base</h4>
<p class="has-line-data" data-line-start="832" data-line-end="833">“slicing” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=836 data-line-end=837><a id="Element_AllergyIntolerancereactionsubstancecodingsnomedCT_836"></a>Element: <em>AllergyIntolerance.reaction.substance.coding:snomedCT</em></h2>
<h3 class="code-line" data-line-start=838 data-line-end=839><a id="Component_max_838"></a>Component: <em>max</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=845 data-line-end=846><a id="Base_845"></a>Base</h4>
<p class="has-line-data" data-line-start="846" data-line-end="847">“max” == *</p>
<h2 class="code-line" data-line-start=850 data-line-end=851><a id="Element_AllergyIntolerancereactionsubstancecodingsnomedCTextension_850"></a>Element: <em>AllergyIntolerance.reaction.substance.coding:snomedCT.extension</em></h2>
<h3 class="code-line" data-line-start=852 data-line-end=853><a id="Component_slicing_852"></a>Component: <em>slicing</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=858 data-line-end=859><a id="Diff_858"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="860" data-line-end="870" class="language-diff">{
  "discriminator": [
    {
      "path": "url",
      "type": "value"
    }
  ],
  "rules": "open"
}  
</code></pre>
<h4 class="code-line" data-line-start=872 data-line-end=873><a id="Base_872"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="874" data-line-end="885" class="language-json">{
  "<span class="hljs-attribute">description</span>": <span class="hljs-value"><span class="hljs-string">"Extensions are always sliced by (at least) url"</span></span>,
  "<span class="hljs-attribute">discriminator</span>": <span class="hljs-value">[
    {
      "<span class="hljs-attribute">path</span>": <span class="hljs-value"><span class="hljs-string">"url"</span></span>,
      "<span class="hljs-attribute">type</span>": <span class="hljs-value"><span class="hljs-string">"value"</span>
    </span>}
  ]</span>,
  "<span class="hljs-attribute">rules</span>": <span class="hljs-value"><span class="hljs-string">"open"</span>
</span>}
</code></pre>
<h2 class="code-line" data-line-start=888 data-line-end=889><a id="Element_AllergyIntolerancereactionsubstancecodingsnomedCTextensionsnomedCTDescriptionID_888"></a>Element: <em>AllergyIntolerance.reaction.substance.coding:snomedCT.extension:snomedCTDescriptionID</em></h2>
<h3 class="code-line" data-line-start=890 data-line-end=891><a id="Component_type_890"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=896 data-line-end=897><a id="Diff_896"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="898" data-line-end="905" class="language-diff">[
  {
    "code": "Extension",
    "profile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid"
  }
]  
</code></pre>
<h4 class="code-line" data-line-start=907 data-line-end=908><a id="Base_907"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="909" data-line-end="915" class="language-json">[
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Extension"</span>
  </span>}
]
</code></pre>
<h2 class="code-line" data-line-start=918 data-line-end=919><a id="Element_AllergyIntolerancereactionsubstancecodingsnomedCTsystem_918"></a>Element: <em>AllergyIntolerance.reaction.substance.coding:snomedCT.system</em></h2>
<h3 class="code-line" data-line-start=920 data-line-end=921><a id="Component_fixedUri_920"></a>Component: <em>fixedUri</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><a href="http://snomed.info/sct">http://snomed.info/sct</a></td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=927 data-line-end=928><a id="Base_927"></a>Base</h4>
<p class="has-line-data" data-line-start="928" data-line-end="929">“fixedUri” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=932 data-line-end=933><a id="Element_AllergyIntolerancereactionsubstancecodingsnomedCTcode_932"></a>Element: <em>AllergyIntolerance.reaction.substance.coding:snomedCT.code</em></h2>
<h3 class="code-line" data-line-start=934 data-line-end=935><a id="Component_min_934"></a>Component: <em>min</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=941 data-line-end=942><a id="Base_941"></a>Base</h4>
<p class="has-line-data" data-line-start="942" data-line-end="943">“min” == 0</p>
<h2 class="code-line" data-line-start=946 data-line-end=947><a id="Element_AllergyIntolerancereactionsubstancecodingsnomedCTdisplay_946"></a>Element: <em>AllergyIntolerance.reaction.substance.coding:snomedCT.display</em></h2>
<h3 class="code-line" data-line-start=948 data-line-end=949><a id="Component_min_948"></a>Component: <em>min</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=955 data-line-end=956><a id="Base_955"></a>Base</h4>
<p class="has-line-data" data-line-start="956" data-line-end="957">“min” == 0</p>
<h2 class="code-line" data-line-start=960 data-line-end=961><a id="Element_AllergyIntolerancereactionmanifestationcoding_960"></a>Element: <em>AllergyIntolerance.reaction.manifestation.coding</em></h2>
<h3 class="code-line" data-line-start=962 data-line-end=963><a id="Component_slicing_962"></a>Component: <em>slicing</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=968 data-line-end=969><a id="Diff_968"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="970" data-line-end="981" class="language-diff">{
  "discriminator": [
    {
      "path": "system",
      "type": "value"
    }
  ],
  "ordered": false,
  "rules": "open"
}  
</code></pre>
<h4 class="code-line" data-line-start=983 data-line-end=984><a id="Base_983"></a>Base</h4>
<p class="has-line-data" data-line-start="984" data-line-end="985">“slicing” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=988 data-line-end=989><a id="Element_AllergyIntolerancereactionmanifestationcodingsnomedCT_988"></a>Element: <em>AllergyIntolerance.reaction.manifestation.coding:snomedCT</em></h2>
<h3 class="code-line" data-line-start=990 data-line-end=991><a id="Component_max_990"></a>Component: <em>max</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=997 data-line-end=998><a id="Base_997"></a>Base</h4>
<p class="has-line-data" data-line-start="998" data-line-end="999">“max” == *</p>
<h2 class="code-line" data-line-start=1002 data-line-end=1003><a id="Element_AllergyIntolerancereactionmanifestationcodingsnomedCTextension_1002"></a>Element: <em>AllergyIntolerance.reaction.manifestation.coding:snomedCT.extension</em></h2>
<h3 class="code-line" data-line-start=1004 data-line-end=1005><a id="Component_slicing_1004"></a>Component: <em>slicing</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1010 data-line-end=1011><a id="Diff_1010"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="1012" data-line-end="1022" class="language-diff">{
  "discriminator": [
    {
      "path": "url",
      "type": "value"
    }
  ],
  "rules": "open"
}  
</code></pre>
<h4 class="code-line" data-line-start=1024 data-line-end=1025><a id="Base_1024"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="1026" data-line-end="1037" class="language-json">{
  "<span class="hljs-attribute">description</span>": <span class="hljs-value"><span class="hljs-string">"Extensions are always sliced by (at least) url"</span></span>,
  "<span class="hljs-attribute">discriminator</span>": <span class="hljs-value">[
    {
      "<span class="hljs-attribute">path</span>": <span class="hljs-value"><span class="hljs-string">"url"</span></span>,
      "<span class="hljs-attribute">type</span>": <span class="hljs-value"><span class="hljs-string">"value"</span>
    </span>}
  ]</span>,
  "<span class="hljs-attribute">rules</span>": <span class="hljs-value"><span class="hljs-string">"open"</span>
</span>}
</code></pre>
<h2 class="code-line" data-line-start=1040 data-line-end=1041><a id="Element_AllergyIntolerancereactionmanifestationcodingsnomedCTextensionsnomedCTDescriptionID_1040"></a>Element: <em>AllergyIntolerance.reaction.manifestation.coding:snomedCT.extension:snomedCTDescriptionID</em></h2>
<h3 class="code-line" data-line-start=1042 data-line-end=1043><a id="Component_type_1042"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1048 data-line-end=1049><a id="Diff_1048"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="1050" data-line-end="1057" class="language-diff">[
  {
    "code": "Extension",
    "profile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid"
  }
]  
</code></pre>
<h4 class="code-line" data-line-start=1059 data-line-end=1060><a id="Base_1059"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="1061" data-line-end="1067" class="language-json">[
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Extension"</span>
  </span>}
]
</code></pre>
<h2 class="code-line" data-line-start=1070 data-line-end=1071><a id="Element_AllergyIntolerancereactionmanifestationcodingsnomedCTsystem_1070"></a>Element: <em>AllergyIntolerance.reaction.manifestation.coding:snomedCT.system</em></h2>
<h3 class="code-line" data-line-start=1072 data-line-end=1073><a id="Component_fixedUri_1072"></a>Component: <em>fixedUri</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><a href="http://snomed.info/sct">http://snomed.info/sct</a></td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1079 data-line-end=1080><a id="Base_1079"></a>Base</h4>
<p class="has-line-data" data-line-start="1080" data-line-end="1081">“fixedUri” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=1084 data-line-end=1085><a id="Element_AllergyIntolerancereactionmanifestationcodingsnomedCTcode_1084"></a>Element: <em>AllergyIntolerance.reaction.manifestation.coding:snomedCT.code</em></h2>
<h3 class="code-line" data-line-start=1086 data-line-end=1087><a id="Component_min_1086"></a>Component: <em>min</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1093 data-line-end=1094><a id="Base_1093"></a>Base</h4>
<p class="has-line-data" data-line-start="1094" data-line-end="1095">“min” == 0</p>
<h2 class="code-line" data-line-start=1098 data-line-end=1099><a id="Element_AllergyIntolerancereactionmanifestationcodingsnomedCTdisplay_1098"></a>Element: <em>AllergyIntolerance.reaction.manifestation.coding:snomedCT.display</em></h2>
<h3 class="code-line" data-line-start=1100 data-line-end=1101><a id="Component_min_1100"></a>Component: <em>min</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1107 data-line-end=1108><a id="Base_1107"></a>Base</h4>
<p class="has-line-data" data-line-start="1108" data-line-end="1109">“min” == 0</p>
<h2 class="code-line" data-line-start=1112 data-line-end=1113><a id="Element_AllergyIntolerancereactionseverity_1112"></a>Element: <em>AllergyIntolerance.reaction.severity</em></h2>
<h3 class="code-line" data-line-start=1114 data-line-end=1115><a id="Component_binding_1114"></a>Component: <em>binding</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1120 data-line-end=1121><a id="Diff_1120"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="1122" data-line-end="1135" class="language-diff">{
  "extension": [
    {
      "url": "http://hl7.org/fhir/StructureDefinition/elementdefinition-bindingName",
      "valueString": "AllergyIntoleranceSeverity"
    }
  ],
  "strength": "required",
  "valueSetReference": {
    "reference": "https://fhir.hl7.org.uk/STU3/ValueSet/CareConnect-ReactionEventSeverity-1"
  }
}  
</code></pre>
<h4 class="code-line" data-line-start=1137 data-line-end=1138><a id="Base_1137"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="1139" data-line-end="1153" class="language-json">{
  "<span class="hljs-attribute">description</span>": <span class="hljs-value"><span class="hljs-string">"Clinical assessment of the severity of a reaction event as a whole, potentially considering multiple different manifestations."</span></span>,
  "<span class="hljs-attribute">extension</span>": <span class="hljs-value">[
    {
      "<span class="hljs-attribute">url</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/elementdefinition-bindingName"</span></span>,
      "<span class="hljs-attribute">valueString</span>": <span class="hljs-value"><span class="hljs-string">"AllergyIntoleranceSeverity"</span>
    </span>}
  ]</span>,
  "<span class="hljs-attribute">strength</span>": <span class="hljs-value"><span class="hljs-string">"required"</span></span>,
  "<span class="hljs-attribute">valueSetReference</span>": <span class="hljs-value">{
    "<span class="hljs-attribute">reference</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/ValueSet/reaction-event-severity"</span>
  </span>}
</span>}
</code></pre>
<h2 class="code-line" data-line-start=1156 data-line-end=1157><a id="Element_AllergyIntolerancereactionexposureRoutecoding_1156"></a>Element: <em>AllergyIntolerance.reaction.exposureRoute.coding</em></h2>
<h3 class="code-line" data-line-start=1158 data-line-end=1159><a id="Component_slicing_1158"></a>Component: <em>slicing</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1164 data-line-end=1165><a id="Diff_1164"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="1166" data-line-end="1177" class="language-diff">{
  "discriminator": [
    {
      "path": "system",
      "type": "value"
    }
  ],
  "ordered": false,
  "rules": "open"
}  
</code></pre>
<h4 class="code-line" data-line-start=1179 data-line-end=1180><a id="Base_1179"></a>Base</h4>
<p class="has-line-data" data-line-start="1180" data-line-end="1181">“slicing” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=1184 data-line-end=1185><a id="Element_AllergyIntolerancereactionexposureRoutecodingsnomedCT_1184"></a>Element: <em>AllergyIntolerance.reaction.exposureRoute.coding:snomedCT</em></h2>
<h3 class="code-line" data-line-start=1186 data-line-end=1187><a id="Component_max_1186"></a>Component: <em>max</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1193 data-line-end=1194><a id="Base_1193"></a>Base</h4>
<p class="has-line-data" data-line-start="1194" data-line-end="1195">“max” == *</p>
<h2 class="code-line" data-line-start=1198 data-line-end=1199><a id="Element_AllergyIntolerancereactionexposureRoutecodingsnomedCTextension_1198"></a>Element: <em>AllergyIntolerance.reaction.exposureRoute.coding:snomedCT.extension</em></h2>
<h3 class="code-line" data-line-start=1200 data-line-end=1201><a id="Component_slicing_1200"></a>Component: <em>slicing</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1206 data-line-end=1207><a id="Diff_1206"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="1208" data-line-end="1218" class="language-diff">{
  "discriminator": [
    {
      "path": "url",
      "type": "value"
    }
  ],
  "rules": "open"
}  
</code></pre>
<h4 class="code-line" data-line-start=1220 data-line-end=1221><a id="Base_1220"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="1222" data-line-end="1233" class="language-json">{
  "<span class="hljs-attribute">description</span>": <span class="hljs-value"><span class="hljs-string">"Extensions are always sliced by (at least) url"</span></span>,
  "<span class="hljs-attribute">discriminator</span>": <span class="hljs-value">[
    {
      "<span class="hljs-attribute">path</span>": <span class="hljs-value"><span class="hljs-string">"url"</span></span>,
      "<span class="hljs-attribute">type</span>": <span class="hljs-value"><span class="hljs-string">"value"</span>
    </span>}
  ]</span>,
  "<span class="hljs-attribute">rules</span>": <span class="hljs-value"><span class="hljs-string">"open"</span>
</span>}
</code></pre>
<h2 class="code-line" data-line-start=1236 data-line-end=1237><a id="Element_AllergyIntolerancereactionexposureRoutecodingsnomedCTextensionsnomedCTDescriptionID_1236"></a>Element: <em>AllergyIntolerance.reaction.exposureRoute.coding:snomedCT.extension:snomedCTDescriptionID</em></h2>
<h3 class="code-line" data-line-start=1238 data-line-end=1239><a id="Component_type_1238"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Nothing to diff, value below</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1244 data-line-end=1245><a id="Diff_1244"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="1246" data-line-end="1253" class="language-diff">[
  {
    "code": "Extension",
    "profile": "https://fhir.hl7.org.uk/STU3/StructureDefinition/Extension-coding-sctdescid"
  }
]  
</code></pre>
<h4 class="code-line" data-line-start=1255 data-line-end=1256><a id="Base_1255"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="1257" data-line-end="1263" class="language-json">[
  {
    "<span class="hljs-attribute">code</span>": <span class="hljs-value"><span class="hljs-string">"Extension"</span>
  </span>}
]
</code></pre>
<h2 class="code-line" data-line-start=1266 data-line-end=1267><a id="Element_AllergyIntolerancereactionexposureRoutecodingsnomedCTsystem_1266"></a>Element: <em>AllergyIntolerance.reaction.exposureRoute.coding:snomedCT.system</em></h2>
<h3 class="code-line" data-line-start=1268 data-line-end=1269><a id="Component_fixedUri_1268"></a>Component: <em>fixedUri</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><a href="http://snomed.info/sct">http://snomed.info/sct</a></td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1275 data-line-end=1276><a id="Base_1275"></a>Base</h4>
<p class="has-line-data" data-line-start="1276" data-line-end="1277">“fixedUri” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=1280 data-line-end=1281><a id="Element_AllergyIntolerancereactionexposureRoutecodingsnomedCTcode_1280"></a>Element: <em>AllergyIntolerance.reaction.exposureRoute.coding:snomedCT.code</em></h2>
<h3 class="code-line" data-line-start=1282 data-line-end=1283><a id="Component_min_1282"></a>Component: <em>min</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1289 data-line-end=1290><a id="Base_1289"></a>Base</h4>
<p class="has-line-data" data-line-start="1290" data-line-end="1291">“min” == 0</p>
<h2 class="code-line" data-line-start=1294 data-line-end=1295><a id="Element_AllergyIntolerancereactionexposureRoutecodingsnomedCTdisplay_1294"></a>Element: <em>AllergyIntolerance.reaction.exposureRoute.coding:snomedCT.display</em></h2>
<h3 class="code-line" data-line-start=1296 data-line-end=1297><a id="Component_min_1296"></a>Component: <em>min</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>1</td>
         <td>Not defined</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1303 data-line-end=1304><a id="Base_1303"></a>Base</h4>
<p class="has-line-data" data-line-start="1304" data-line-end="1305">“min” == 0</p>
<h2 class="code-line" data-line-start=1308 data-line-end=1309><a id="Element_AllergyIntoleranceextensionallergyIntoleranceEnd_1308"></a>Element: <em>AllergyIntolerance.extension:allergyIntoleranceEnd</em></h2>
<h3 class="code-line" data-line-start=1310 data-line-end=1311><a id="Component_type_1310"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Not defined</td>
         <td>Nothing to diff, value below</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1316 data-line-end=1317><a id="Diff_1316"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="1318" data-line-end="1327" class="language-diff">[
  {
    "code": "Extension",
    "targetProfile": [
      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/Extension-UKCore-AllergyIntoleranceEnd"
    ]
  }
]  
</code></pre>
<h4 class="code-line" data-line-start=1329 data-line-end=1330><a id="Base_1329"></a>Base</h4>
<p class="has-line-data" data-line-start="1330" data-line-end="1331">“type” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=1334 data-line-end=1335><a id="Element_AllergyIntolerancecode_1334"></a>Element: <em>AllergyIntolerance.code</em></h2>
<h3 class="code-line" data-line-start=1336 data-line-end=1337><a id="Component_binding_1336"></a>Component: <em>binding</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Not defined</td>
         <td>Nothing to diff, value below</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1342 data-line-end=1343><a id="Diff_1342"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="1344" data-line-end="1349" class="language-diff">{
  "strength": "extensible",
  "valueSet": "https://fhir.simplifier.net/HL7FHIRUKCoreR4/ValueSet/UKCore-AllergyCode"
}  
</code></pre>
<h4 class="code-line" data-line-start=1351 data-line-end=1352><a id="Base_1351"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="1353" data-line-end="1367" class="language-json">{
  "<span class="hljs-attribute">description</span>": <span class="hljs-value"><span class="hljs-string">"Type of the substance/product, allergy or intolerance condition, or negation/exclusion codes for reporting no known allergies."</span></span>,
  "<span class="hljs-attribute">extension</span>": <span class="hljs-value">[
    {
      "<span class="hljs-attribute">url</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/elementdefinition-bindingName"</span></span>,
      "<span class="hljs-attribute">valueString</span>": <span class="hljs-value"><span class="hljs-string">"AllergyIntoleranceCode"</span>
    </span>}
  ]</span>,
  "<span class="hljs-attribute">strength</span>": <span class="hljs-value"><span class="hljs-string">"example"</span></span>,
  "<span class="hljs-attribute">valueSetReference</span>": <span class="hljs-value">{
    "<span class="hljs-attribute">reference</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/ValueSet/allergyintolerance-code"</span>
  </span>}
</span>}
</code></pre>
<h2 class="code-line" data-line-start=1370 data-line-end=1371><a id="Element_AllergyIntolerancepatientidentifierassigner_1370"></a>Element: <em>AllergyIntolerance.patient.identifier.assigner</em></h2>
<h3 class="code-line" data-line-start=1372 data-line-end=1373><a id="Component_type_1372"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Not defined</td>
         <td>Nothing to diff, value below</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1378 data-line-end=1379><a id="Diff_1378"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="1380" data-line-end="1389" class="language-diff">[
  {
    "code": "Reference",
    "targetProfile": [
      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Organization"
    ]
  }
]  
</code></pre>
<h4 class="code-line" data-line-start=1391 data-line-end=1392><a id="Base_1391"></a>Base</h4>
<p class="has-line-data" data-line-start="1392" data-line-end="1393">“type” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=1396 data-line-end=1397><a id="Element_AllergyIntoleranceencounter_1396"></a>Element: <em>AllergyIntolerance.encounter</em></h2>
<h3 class="code-line" data-line-start=1398 data-line-end=1399><a id="Component_type_1398"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Not defined</td>
         <td>Nothing to diff, value below</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1404 data-line-end=1405><a id="Diff_1404"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="1406" data-line-end="1415" class="language-diff">[
  {
    "code": "Reference",
    "targetProfile": [
      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Encounter"
    ]
  }
]  
</code></pre>
<h4 class="code-line" data-line-start=1417 data-line-end=1418><a id="Base_1417"></a>Base</h4>
<p class="has-line-data" data-line-start="1418" data-line-end="1419">“type” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=1422 data-line-end=1423><a id="Element_AllergyIntoleranceencounteridentifierassigner_1422"></a>Element: <em>AllergyIntolerance.encounter.identifier.assigner</em></h2>
<h3 class="code-line" data-line-start=1424 data-line-end=1425><a id="Component_type_1424"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Not defined</td>
         <td>Nothing to diff, value below</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1430 data-line-end=1431><a id="Diff_1430"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="1432" data-line-end="1441" class="language-diff">[
  {
    "code": "Reference",
    "targetProfile": [
      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Organization"
    ]
  }
]  
</code></pre>
<h4 class="code-line" data-line-start=1443 data-line-end=1444><a id="Base_1443"></a>Base</h4>
<p class="has-line-data" data-line-start="1444" data-line-end="1445">“type” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=1448 data-line-end=1449><a id="Element_AllergyIntolerancerecorderidentifierassigner_1448"></a>Element: <em>AllergyIntolerance.recorder.identifier.assigner</em></h2>
<h3 class="code-line" data-line-start=1450 data-line-end=1451><a id="Component_type_1450"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Not defined</td>
         <td>Nothing to diff, value below</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1456 data-line-end=1457><a id="Diff_1456"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="1458" data-line-end="1467" class="language-diff">[
  {
    "code": "Reference",
    "targetProfile": [
      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Organization"
    ]
  }
]  
</code></pre>
<h4 class="code-line" data-line-start=1469 data-line-end=1470><a id="Base_1469"></a>Base</h4>
<p class="has-line-data" data-line-start="1470" data-line-end="1471">“type” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=1474 data-line-end=1475><a id="Element_AllergyIntoleranceasserteridentifierassigner_1474"></a>Element: <em>AllergyIntolerance.asserter.identifier.assigner</em></h2>
<h3 class="code-line" data-line-start=1476 data-line-end=1477><a id="Component_type_1476"></a>Component: <em>type</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Not defined</td>
         <td>Nothing to diff, value below</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1482 data-line-end=1483><a id="Diff_1482"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="1484" data-line-end="1493" class="language-diff">[
  {
    "code": "Reference",
    "targetProfile": [
      "https://fhir.simplifier.net/HL7FHIRUKCoreR4/StructureDefinition/UKCore-Organization"
    ]
  }
]  
</code></pre>
<h4 class="code-line" data-line-start=1495 data-line-end=1496><a id="Base_1495"></a>Base</h4>
<p class="has-line-data" data-line-start="1496" data-line-end="1497">“type” is not defined in the base element definition.</p>
<h2 class="code-line" data-line-start=1500 data-line-end=1501><a id="Element_AllergyIntolerancereactionsubstance_1500"></a>Element: <em>AllergyIntolerance.reaction.substance</em></h2>
<h3 class="code-line" data-line-start=1502 data-line-end=1503><a id="Component_binding_1502"></a>Component: <em>binding</em></h3>
<table class="table table-striped table-bordered">
   <thead>
      <tr>
         <th>CareConnect-AllergyIntolerance-1</th>
         <th>UKCoreAllergyIntolerance</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>Not defined</td>
         <td>Nothing to diff, value below</td>
      </tr>
   </tbody>
</table>
<h4 class="code-line" data-line-start=1508 data-line-end=1509><a id="Diff_1508"></a>Diff</h4>
<pre><code class="has-line-data" data-line-start="1510" data-line-end="1515" class="language-diff">{
  "strength": "extensible",
  "valueSet": "https://fhir.simplifier.net/HL7FHIRUKCoreR4/ValueSet/UKCore-AllergySubstance"
}  
</code></pre>
<h4 class="code-line" data-line-start=1517 data-line-end=1518><a id="Base_1517"></a>Base</h4>
<pre><code class="has-line-data" data-line-start="1519" data-line-end="1533" class="language-json">{
  "<span class="hljs-attribute">description</span>": <span class="hljs-value"><span class="hljs-string">"Codes defining the type of the substance (including pharmaceutical products)."</span></span>,
  "<span class="hljs-attribute">extension</span>": <span class="hljs-value">[
    {
      "<span class="hljs-attribute">url</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/StructureDefinition/elementdefinition-bindingName"</span></span>,
      "<span class="hljs-attribute">valueString</span>": <span class="hljs-value"><span class="hljs-string">"SubstanceCode"</span>
    </span>}
  ]</span>,
  "<span class="hljs-attribute">strength</span>": <span class="hljs-value"><span class="hljs-string">"example"</span></span>,
  "<span class="hljs-attribute">valueSetReference</span>": <span class="hljs-value">{
    "<span class="hljs-attribute">reference</span>": <span class="hljs-value"><span class="hljs-string">"http://hl7.org/fhir/ValueSet/substance-code"</span>
  </span>}
</span>}
</code></pre>