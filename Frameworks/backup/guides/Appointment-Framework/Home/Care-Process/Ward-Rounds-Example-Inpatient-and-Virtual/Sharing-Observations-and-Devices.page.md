## {{page-title}}


Most EPR's will use their own native API's to both record and read data. When it comes to sharing the data or accessing EHR data via 3rd party applications such as a HIE, mobile application, Clinical Portal, etc, we start to find standards. The most common standard in this area in the UK is HL7 FHIR (see IHE QEDM below).

In addition we have devices which may have limited storage or display capabilties (e.g. a finger SPO2 monitor) and the observations need transfering to a EPR/PHR which handles this.


 <div markdown="span" class="alert alert-warning" role="information">
<p>Robert's viewed his SPO2 measurements in his PHR app, this measurement was orignially captured on a device connected to the PHR.</p>
</div>

 <div markdown="span" class="alert alert-warning" role="information">
<p>Other care providers (e.g. long term COVID) would want to monitor Roberts condition while he was at home.</p>
</div>


 <div markdown="span" class="alert alert-warning" role="information">
<p>During the ED stage of Robert's journey, he was monitored by bedside devices which automatically populated data in the trusts EPR system.</p>
</div>

 <div markdown="span" class="alert alert-warning" role="information">
<p>Clinicians would review the Roberts progress during ward rounds. This was done on mobile device using charting/portal applications which directly accessed the trusts EPR record.</p>
</div>

 <div markdown="span" class="alert alert-warning" role="information">
<p>Other care providers and carers may wish to view Roberts progress (the observation data) during his hospital stay</p>
</div>


These use cases are quite different for the data capture which tended to focus around terms like NEWS2 or Vital Signs. 
Similarly standards used may be different. Several approaches are listed below:

| Standard | Description |
|--
| [HL7 v2 Unsolicited transmission of an observation message (ORU_R01)](https://hl7-definition.caristix.com/v2/HL7v2.5.1/TriggerEvents/ORU_R01) | The ORU was designed for transmitting laboratory results to other systems but it has been used by devices to send observations to both GP and Hospital systems in the UK |
| [HL7 FHIR Personal Health Device Implementation Guide](https://build.fhir.org/ig/HL7/phd/index.html) | This Implementation Guide (IG) defines the use of FHIR resources to convey measurements and supporting data from communicating Personal Health Devices (PHDs) to receiving systems for electronic medical records, clinical decision support, and medical data archiving for aggregate quality measurement and research purposes. | 
| {{pagelink:Home/Technical-Framework/Query-API}} | The client runs a HL7 FHIR based query which takes several parameters to return the observations they are interested in | 
