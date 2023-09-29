## {{page-title}}


 <div markdown="span" class="alert alert-warning" role="information"><p>Robert Brown is a clinically obese patient who also has long term COVID. 
He has started to feel unwell, and his breathing was becoming shallow. 
His partner Bridget suggests he takes a SPO2 measurement using equipment supplied for home monitoring of long term COVID.</p>
<p>The reading is low and after consultation with NHS 111, Robert is admitted to St James hospital for emergency treatment.</p>
<p>Robert is diagnosed as having a potential blood clot, anticoagulant medications are administered and has a CT scan. </p>
<p>Robert is kept in for observation and is transferred to an observation ward, his breathing returns to normal and no blood clot is found. Robert is then discharged from hospital</p>
</div>

### Observation 'Round'

Traditionally Robert's records during his hospital inpatient stay would have been located at the end of his bed. The chart shown in the diagram below is recording [NEWS2 Observations](https://www.england.nhs.uk/ourwork/clinical-policy/sepsis/nationalearlywarningscore/). NEWS2 (and also vital signs) contain a series of observations such as:

- Respiratory Rate
- Oxygen Saturation (SPO2)
- Blood Pressure
- Heart Rate
- Body Temperature

These observations are normally taken during a nursing observation round and is normally presented to practitioners on a chart.

{{render:diagrams-EHR-Record-Types-bedchart}}

These observations are also collected in other settings, these may be better described as `Vital Signs` as NEWS2 is defined type of Vital Signs. These include:

- GP Practice
- Community
- Emegency 
- Miltitary ambulatory care


#### Recording Observations

Modern technology has given us new methods for capturing these observations alongside paper based forms.

On ward rounds, a nurse will likely record these observations in an application such as the example below. This form also automatically calculates a NEWS2 score from the observation values entered:

{{render:diagrams-EHR-Record-Types-news2form}}

It is also possible devices are used to gather these observations. This device is recording: SPO2, Heart Rate, Blood Pressure and Respiratory rate. 
A connected device would be able to automatically populate the form or the nurse can copy the values into the form.



<table>
  <tr>
   <td> 
{{render:diagrams-EHR-Record-Types-vital-signs-monitoring}}
   </td>
   <td>
{{render:diagrams-EHR-Record-Types-blood-pressure-monitor}}
   </td>
   </tr>
</table>



Citizens are also capturing and recording these observations. In the use case Robert had been issued an SPO2 measuring device, it's also possible he had personnel equipment which automtically recorded this and other observations.

Similar to use of devices in hospital setting, their can be electronic communication between the devices and the record system (e.g. Apple Health, Google Fit, etc)

<table>
  <tr>
   <td> 
{{render:diagrams-EHR-Record-Types-Observations-Apple}}
   </td>
   <td>
{{render:diagrams-EHR-Record-Types-spo2}}
   </td>
   <td>
{{render:diagrams-EHR-Record-Types-withingspressuremonitor}}
   </td>
   </tr>
</table>

### Displaying Observations

Observations are typically displayed to practitioners and citizens as charts. This is very similar to the bed charts we discussed earlier.

<table>
  <tr>
   <td> 
 {{render:diagrams-EHR-Record-Types-NEWS2-Observation-Chart}}
   </td>
    <td> 
 {{render:diagrams-EHR-Record-Types-googlefit}}
   </td>
   </tr>
</table>


