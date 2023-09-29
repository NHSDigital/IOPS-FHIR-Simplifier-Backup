## {{page-title}}

A bundle should be sent including the Patient and Encounter resources as a minimum. The {{pagelink:Home/FHIR-Assets/All-assets/Profiles/GPConnect-StructuredRecord-Bundle-1}}

<table data-responsive>
    <thead>
        <tr>
            <th>Profile</th>
            <th>Optionality</th>
            <th data-no-sort>Cardinality</th>
        </tr>
    </thead>
    
   
   <!--CareConnect-GPC-Patient-->
    <tbody>
      
        <tr>
            <td class="nhsd-t-body">
                {{pagelink:Home/FHIR-Assets/All-assets/Profiles/CareConnect-GPC-Patient-1}}
            </td>
            <td class="nhsd-t-body"><span class="mro-circle mandatory"></span> Mandatory</td>
            <td class="nhsd-t-body"><code>1..1</code></td>
        </tr>
       
       
       
         <!--CareConnect-GPC-Encounter-1-->
        <tr>
            <td class="nhsd-t-body">
                {{pagelink:Home/FHIR-Assets/All-assets/Profiles/CareConnect-GPC-Encounter-1}}
            </td>
            <td class="nhsd-t-body"><span class="mro-circle mandatory"></span> Mandatory</td>
            <td class="nhsd-t-body"><code>1..1</code></td>
        </tr>
      
      
       <!--CareConnect-GPC-Observation-1-->
        <tr>
            <td class="nhsd-t-body">
                {{pagelink:Home/FHIR-Assets/All-assets/Profiles/CareConnect-GPC-Observation-1}}
            </td>
            <td class="nhsd-t-body"><span class="mro-circle optional"></span> Optional</td>
            <td class="nhsd-t-body"><code>0..*</code></td>
        </tr>
       <!--CareConnect-GPC-MedicationStatement-1-->
        <tr>
            <td class="nhsd-t-body">
                {{pagelink:Home/FHIR-Assets/All-assets/Profiles/CareConnect-GPC-MedicationStatement-1 }}
            </td>
            <td class="nhsd-t-body"><span class="mro-circle optional"></span> Optional</td>
            <td class="nhsd-t-body"><code>0..*</code></td>
        </tr>
               <!--CareConnect-GPC-Organization-1-->
        <tr>
            <td class="nhsd-t-body">
                {{pagelink:Home/FHIR-Assets/All-assets/Profiles/CareConnect-GPC-Organization-1 }}
            </td>
            <td class="nhsd-t-body"><span class="mro-circle optional"></span> Optional</td>
            <td class="nhsd-t-body"><code>0..*</code></td>
        </tr>
               <!--CareConnect-GPC-Practitioneer-1-->
        <tr>
            <td class="nhsd-t-body">
                {{pagelink:Home/FHIR-Assets/All-assets/Profiles/CareConnect-GPC-Practitioner }}
            </td>
            <td class="nhsd-t-body"><span class="mro-circle optional"></span> Optional</td>
            <td class="nhsd-t-body"><code>0..*</code></td>
        </tr>
  
   
</table>

<br>
<br>

## Further Information

### Optionality and Cardinality

**Optionality** and **Cardinality**, please refer to the [Labels used within this guidance](https://simplifier.net/guide/GP-Connect-Update-record/Home/Introduction/How-to-use-this-implementation-guide?version=current#Labels-used-within-this-guidance) as well as the information referred to in the {{pagelink:Home/Introduction/How-to-use-this-implementation-guide}} for further details

### Consent

The **meta.security** item within each of the profiles will be used to record a patient consent flag.  Where there is a value present (The patient has consented to their details **not** to be shared). 

**Please note:** The meta.security item, represented in each of the profiles referred to in this specification will record the security label item referred to below.

 * Full details of an Encounter are sent without security label - Patient consents for Updating Patient Record and sharing on Patient Facing Services
* Full details of an Encounter are sent with security label - Patient consents for Updating Patient Record but does not consent to share on Patient Facing Services
* Full details of an Encounter are not sent - Patient does not consent to Update Record and therefore also does not consent to share on Patient Facing Services (log encounter but don’t add full details to patient record)