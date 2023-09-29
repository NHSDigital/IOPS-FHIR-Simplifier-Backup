## {{page-title}}

 <div markdown="span" class="alert alert-warning" role="information">
<p>Robert is kept in for observation and is transferred to an observation ward, his breathing returns to normal and no blood clot is found. Robert is then discharged from hospital</p>
</div>

A secondary care hospital/trust will use a mix of different systems. Some of these systems are specific to specialty such as radiology/imaging, emergency, pathology/laboratory, etc systems. 

These systems will often need to hold copies of the same information, typically this is around patient demographics, encounters and appointments. 

We have a need to keep users of these systems informed of key changes and keep this data synchronised accross the system. These events and the data is known as `admission, discharges, and transfers (ADT)`. Technically these are also known as `Events`.

By far the most common standard in this area (especially in Acute NHS Trusts/Boards) is:

<table>
  <tr>
    <th>Standard</th>
    
    <th>Event</th>
  </tr>
  <tr>
    <td>
HL7 v2
    </td>
   
    <td>Admission, Discharge and Transfer. 

<a href="https://github.com/NHSDigital/IOPS-Frameworks/blob/main/documents/HSCIC%20ITK%20HL7%20V2%20Message%20Specifications.pdf">NHS England HL7 V2 Message Specifications</a></td>
  </tr>
</table>

<div markdown="span" class="alert alert-warning" role="information"><i class="fa fa-information"></i><b> Important:</b> The term HL7 is commonly used to refer to the HL7 v2 standard. It will not refer to V3, CDA, FHIR or HL7.</div>


This standard is based on pre JSON/XML encoding format, called [pipe and hat](https://en.wikipedia.org/wiki/Health_Level_7). 

```
MSH|^~\&|PAS|RCB|ROUTE|ROUTE|201010101418||ADT^A01^ADT_A01|1391320453338055|P|2.4|1|20101010141857|||GBR|UNICODE|EN||iTKv1.0
EVN||201010101400|||111111111^Cortana^Emily^^^Miss^^RCB55|201010101400
PID|1||3333333333^^^NHS||SMITH^FREDRICA^J^^MRS^^L|SCHMIDT^HELGAR^Y|196512131515|2|||29 WEST AVENUE^BURYTHORPE^MALTON^NORTH YORKSHIRE^YO32 5TT^GBR^H||+441234567890||EN|M|C22|||||A|Berlin|||GBR||DEU
PD1|||MALTON GP PRACTICE^^Y06601|G5612908^Townley^Gregory^^^Dr^^^GMC
PV1|1|I|RCB^OBS1^BAY2-6^RCB55|13|||C3456789^Darwin^Samuel^^^Dr^^^GMC|G5612908^Townley^Gregory^^^Dr^^^GMC|C3456789^Darwin^Samuel^^^Dr^^^GMC|300||||19|||||2139^^^VISITID|||||||||||||||||||||||||201010201716
```

Some examples of events messages sent during Roberts stay are shown in the table below:

| Event Message (ADT) | Plain version |
|--
| Patient Admission (ADT_A01) | <div markdown="span" class="alert alert-warning" role="information">Robert Brown (NHS Number 9876543210) has had an emergency admission to the Emergency Dept of St James Hospital Leeds Teaching NHS Trust on 15 Jun 2023 at 1615</div> |
| Patient Transfer (ADT_A02) | <div markdown="span" class="alert alert-warning" role="information">Robert Brown (NHS Number 9876543210) has been transferred from the Emergency Dept of St James Hospital Leeds Teaching NHS Trust to the Observation Ward on 15 Jun 2023 at 1945</div> |
| Patient Discharge (ADT_A03) | <div markdown="span" class="alert alert-warning" role="information">Robert Brown (NHS Number 9876543210) has been discharged as an inpatient from the Observation Ward of St James Hospital Leeds Teaching NHS Trust ot 17 Jun 2023 at 1153</div> |
| Register Outpatient (Encounter) (ADT_A04) | <div markdown="span" class="alert alert-warning" role="information">Robert Brown (NHS Number 9876543210) has had a follow up outpatient encounter with Leeds Teaching NHS Trust on 20 Jun 2023 at 1533</div> |

NHS Trusts will normally use a system called Trust Integration Engine (TIE) to handle the broadcasting (distribution and transformation) of these event messages.

This event messaging can also be extended to other care settings, for example several GP systems accept HL7 v2 messages and this has been done by several NHS Trusts including Mid Yorkshire Hospitals NHS Trust. This allows both GP and Community practitioners to be aware of the patients current situation. 



