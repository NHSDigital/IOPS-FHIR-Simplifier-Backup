## {{page-title}}

This glossary gives a short definition of terms used in this implementation guide. Links are supplied to websites where further information which may help the reader can be found. 

<div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-information"></i><h4> Disclaimer</h4>
Where the link to further reading is provided by the NHSE Development team is to an external website it is done with the best intentions, however the NHSE Development team cannot guarantee the accuracy of the information supplied, and is not responsible for the contents of any external internet sites listed.
 </div>

<b>
<a href=#A>A</a>
B
<a href=#C>C</a>
<a href=#D>D</a>
<a href=#E>E</a>
<a href=#F>F</a>
<a href=#G>G</a>
<a href=#H>H</a>
<a href=#I>I</a>
<a href=#J>J</a>
K
<a href=#L>L</a>
<a href=#M>M</a>
<a href=#N>N</a>
<a href=#O>O</a>
<a href=#P>P</a>
Q
<a href=#R>R</a>
<a href=#S>S</a>
<a href=#T>T</a>
<a href=#U>U</a>
<a href=#V>V</a>
W
<a href=#X>X</a>
Y
Z
</b>
<br>
<br>


<table class="assets" class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="A">A</h2></td>
</tr>
<tr>
<td>Accreditation</td>
<td>The action or process used to ensure that a system provider meets necessary criteria to use the Open API services.</td>
<td><br></td>
</tr>
<tr>
<td>ACF</td>
<td>Access Control Framework. Access to NHS Care Records Service data (on Spine) is controlled by the ACF which registers and authenticates all users. It provides a single log-in and a record of each healthcare professional accessing a patient’s NHS care record.
<br><br>
All information is provided on a need-to-know basis and based on a user’s role and legitimate relationship with the patient. It stores the details of those relationships between healthcare professionals and patients, as well as patient preferences on information sharing (such as whether certain sensitive information is restricted from routine sharing).</td>
<td><br></td>
</tr>
<tr>
<td>ACS</td>
<td>Access Control Service. The Access Control Service used on Spine.</td>
<td><br></td>
</tr>
<tr>
<td>Act</td>
<td>A class in HL7 that describes if something happened or may happen.</td>
<td><br></td>
</tr>
<tr>
<td>Active patient</td>
<td>An Active patient as defined by GP Connect is any patient on a providers system that has Not Left and is Not Deceased. The concept of Active is related to the patient’s registration status rather than to the patients registration type.
<br><br>
A provider's system may have a number of different statuses which should be considered Active. Many of those statuses may apply to a number of different registration type. Below is a basic example of a possible GP Practice representation of patient registration type and registration status, to help explain the concept of an Active patient within GP Connect.</td>
<td><br></td>
</tr>
<tr>
<td>ActRelationship</td>
<td>A relationship between two HL7 act classes.</td>
<td><br></td>
</tr>
<tr>
<td>ADRT</td>
<td>Advance Decision to Refuse Treatment. An advance decision (sometimes known as an advance decision to refuse treatment, an ADRT, or a living will) is a decision you can make now to refuse a specific type of treatment at some time in the future.</td>
<td><br></td>
</tr>
<tr>
<td>ADT</td>
<td>HL7 Admit/Discharge and Transfer messages carry patient demographic information for HL7 communications but also provide important information about trigger events (such as patient admit, discharge, transfer, registration, etc.).
<br><br>
Some of the most important segments in the ADT message are the PID segment, the PV1 (Patient Visit). ADT messages are extremely common in HL7 processing and are among the most widely used of all message types.</td>
<td><br></td>
</tr>
<tr>
<td>AoMRC</td>
<td>The Academy of Medical Royal Colleges speaks on standards of care and medical education across the UK and drives improvement in health and patient care through education, training and quality standards.</td>
<td><br></td>
</tr>
<tr>
<td>API</td>
<td>The term Application Programming Interface is quite a confused term in the context of FHIR. Strictly speaking, an API is a set or services offered by a programming library that can be made use of by another application. Historically these would have been made available from a single machine although now they are available across networks.
<br><br>
In the service/message/document categorisation, an API is a service interface. As technology became increasingly capable of supporting distributed operations, the differences between SOA (Service Oriented Architecture) and API became blurred. In the context of FHIR we define APIs as REST based interfaces.</td>
<td><br></td>
</tr>
<tr>
<td>Application acknowledgement
</td>
<td>A response from one application to another indicating that a message has been received and is valid.</td>
<td><br></td>
</tr>
<tr>
<td>Application role
</td>
<td>The role played by the application in a particular interaction.</td>
<td><br></td>
</tr>
<tr>
<td>Argonaut</td>
<td>An initiative launched by HL7 to accelerate the development and adoption of FHIR. Supported by 11 organizations, including EHR vendors Epic and Cerner and health systems Mayo Clinic and Intermountain Healthcare.</td>
<td><br></td>
</tr>
<tr>
<td>ASID</td>
<td>Accredited System Identifier is an identifier used in Spine Directory Service (SDS) to reference an IT system that has been accredited for use in a specific health or care organisation.</td>
<td><br></td>
</tr>
<tr>
<td>Assurance</td>
<td>A set of activities intended to provide confidence that a system works as described and in a safe and secure way.</td>
<td><br></td>
</tr>
<tr>
<td>Attributes</td>
<td>Attributes are abstractions of the data captured about classes. Attributes capture separate aspects of the class and take their values independent of one another.</td>
<td><br></td>
</tr>
<tr>
<td>AUS</td>
<td>An Authenticated User Session is defined as when a real person is physically logged in to a system after being authenticated via their smart card or by another authentication method.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets" class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="C">C</h2></td>
</tr>
<tr>
<td>CareConnect</td>
<td>CareConnect assets were developed in HL7® FHIR STU3 collaboratively by HL7 and the INTEROPen community with NHS England as the development partner.</td>
<td><a href="https://simplifier.net/guide/careconnectversionhistory/home" target="_blank">More about CareConnect</a><br></td>
</tr>
<tr>
<td>Care Record Element (CRE)
</td>
<td>Care Record Elements (CREs) are used by the Spine to identify Medication and Allergies and Adverse Reactions.</td>
<td><br></td>
</tr>
<tr>
<td>CCDA</td>
<td>Consolidated CDA is an XML based implementation guide that specifies encoding, structure and semantics for a document that summarises a single patient’s clinical information.</td>
<td><br></td>
</tr>
<tr>
<td>CCG</td>
<td>Now replaced by <a href="https://www.england.nhs.uk/integratedcare/what-is-integrated-care/" target="_blank">Integrated Care Systems (ICSs)</a>, the Clinical Commissioning Group was an NHS organisation made up of GP practices looking to understand the health needs of local people and use funds given by NHS England to buy services which meet those needs. </td>
<td><br></td>
</tr>
<tr>
<td>CDA</td>
<td>The Clinical Document Architecture provides an exchange model for clinical documents (such as discharge summaries and progress notes). By leveraging the use of XML, the HL7 V3 Reference Information Model (RIM) and coded vocabularies, CDA makes documents both machine-readable and human-readable. It guarantees preservation of the content by using the extensible Mark-up Language (XML) standard.</td>
<td><br></td>
</tr>
<tr>
<td>CIB</td>
<td>The Code 4 Health, Community Interoperability Board was established early in 2016. This network of networks has taken on a leadership role across the service to coordinate and deliver working interoperability standards.</td>
<td><br></td>
</tr>
<tr>
<td>CIMI</td>
<td>Clinical Information Modelling Initiative An international collaboration dedicated to providing a common format for detailed specifications for the representation of health information content. In this way semantically, interoperable information may be created and shared in health records, messages, and documents.</td>
<td><br></td>
</tr>
<tr>
<td>Class clone</td>
<td>A class that is a clone of another class, derived from another class.</td>
<td><br></td>
</tr>
<tr>
<td>Clinical Safety Officer (CSO)
</td>
<td>A CSO is the person responsible for making sure a software supplier addresses the requirements of DCB0129.</td>
<td><br></td>
</tr>
<tr>
<td>Coded With Extensions (CWE)</td>
<td>The coded attribute allows local codes or user entered text to be sent when the concept that the user would like to express is not a member of the defined value set. If the concept that the user wants to express is represented by a code in the standard value set, the standard code SHALL be sent. The local code can be sent in addition to the standard code if desired. Only if the concept that the user wants to express is NOT represented by a standard code, can a solitary local code be sent.</td>
<td><br></td>
</tr>
<tr>
<td>Coded with No Extensions (CNE)</td>
<td>The coded attribute allows only concepts from the defined value set. No extensions are allowed.</td>
<td><br></td>
</tr>
<tr>
<td>Common Assessment Framework (CAF)</td>
<td>The Common Assessment Framework (CAF) for Adults is a Department of Health funded project that aims to improve information sharing across organisations for multi-disciplinary assessment and care and support planning.</td>
<td><br></td>
</tr>
<tr>
<td>Common Assurance Process (CAP)</td>
<td>The Common Assurance Process (CAP) is an NHS process that needs to be followed to gain accreditation allowing for connection directly to the Spine.</td>
<td><br></td>
</tr>
<tr>
<td>Common Message Element Type (CMET)</td>
<td>This is a reusable model which can be used in multiple messages. CMETs can speed up the process of developing messages and increase consistency between different specifications.</td>
<td><br></td>
</tr>
<tr>
<td><h5 id="G8">Configuration Management</h5></td>
<td>Configuration management is a process for establishing consistency of a product’s attributes throughout its life. In the UK Core, configuration management is a management process that tracks individual configuration items of the UK Core. The UK Core is composed of FHIR® assets that vary in granularity. The UK Core Configuration management helps the development team build a robust and stable implementation guide through the use of tools that automatically manage and monitor updates to configuration data. </td>
<td><a href="https://en.wikipedia.org/w/index.php?title=Configuration_management&oldid=1034511535" target="_blank">More about Configuration</a></td>
</tr>
<tr>
<td>Connection Agreement (CA)</td>
<td>A legal document that must be signed by the software supplier to confirm they understand and will adhere to their obligations when using an API.</td>
<td><br></td>
</tr>
<tr>
<td>Consumer</td>
<td>A system which consumes data using existing Open APIs.
</td>
<td><br></td>
</tr>
<tr>
<td>CP-IS</td>
<td>Child Protection Information Sharing service. An on-line service that allows NHS unscheduled care services to access basic child protection information that has been provided by the Local Authority Children’s Services departments. The NHS is only able to see that a child or foetus has a Child Protection Plan or is in the Looked After system. The information provided is start, end and delete dates; plus a Children’s Services contact telephone number where the NHS can get further information. Basic information about NHS accesses is also passed back to Children’s Services.
</td>
<td><br></td>
</tr>
<tr>
<td>CPR</td>
<td>Cardiopulmonary Resuscitation. Emergency treatment that supports the circulation of blood and/or air in the event of a respiratory and/or cardiac arrest.</td>
<td><br></td>
</tr>
<tr>
<td>CRI</td>
<td>Clinical Referral Information.</td>
<td><br></td>
</tr>

</table>
<br><br>
<table class="assets" class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="D">D</h2></td>
</tr>
<tr>
<td>Data Security and Protection Toolkit (DSPT)
</td>
<td>The Data Security and Protection Toolkit (DSPT) is an online self-assessment tool that all organisations must use if they have access to NHS patient data and systems. Completing the DSPT is part of the developer onboarding process.</td>
<td><br></td>
</tr>
<tr>
<td>Data Type
</td>
<td>The structural format of the data carried in an attribute. Every data element has a data type. Data types define the meaning (semantics) of data values that can be assigned to a data element. Meaningful exchange of data requires that we know the definition of values so exchanged. This is true for complex values such as business messages as well as for simpler values such as character strings or integer numbers.</td>
<td><br></td>
</tr>
<tr>
<td>Data Type Flavour
</td>
<td>A subdivision of a particular data type, that will constrain that particular data type. Data type flavour titles are suffixed with (f).</td>
<td><br></td>
</tr>
<tr>
<td><h5 id="dmd">dm+d</h5></td>
<td>The dm+d is a dictionary of descriptions and codes which represent medicines and devices in use across the NHS.</td>
<td><a href="https://www.nhsbsa.nhs.uk/pharmacies-gp-practices-and-appliance-contractors/dictionary-medicines-and-devices-dmd" target="_blank">More about dm+d</a></td>
</tr>
</table>

<br><br>
<table class="assets" class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="E">E</h2></td>
</tr>
<tr>
<td>ebXML</td>
<td>ebXML (Electronic Business XML) is a project to use the eXtensible Markup Language to standardise the secure exchange business data. Amongst other purposes, ebXML encompasses the standard known as Electronic Data Interchange (EDI).</td>
<td><br></td>
</tr>
<tr>
<td>EEA</td>
<td>European Economic Area.</td>
<td><br></td>
</tr>
<tr>
<td>EHIC</td>
<td>Electronic Health Insurance Card.</td>
<td><br></td>
</tr>
<tr>
<td>EHR</td>
<td>Electronic Healthcare Record. This is the concept of electronic longitudinal collection of patient’s health and health care from cradle to grave. It combines information from different care settings held in different systems and in some instances, aggregates the data and shows them as a single record. It is a record in digital format that is capable of being shared across different health care settings, by being embedded in network-connected enterprise-wide information systems.</td>
<td><br></td>
</tr>
<tr>
<td>EUD
</td>
<td>End User Declaration.</td>
<td><br></td>
</tr>
<tr>
<td>EUO</td>
<td>The End User Organisation is the organisation that will deploy the Supplier System/Product for use by healthcare professionals in delivering patient or client care. </td>
<td><br></td>
</tr>
<tr>
<td>Entity</td>
<td>A class in HL7 that describes a person, animal, organisation or thing.</td>
<td><br></td>
</tr>
<tr>
<td>EPR</td>
<td>An Electronic Patient Record is an electronic record of periodic health care of a single individual, provided mainly by one institution.</td>
<td><br></td>
</tr>
<tr>
<td>EPS</td>
<td>The Electronic Prescription Service enables prescribers, such as GPs and practice nurses, to send prescriptions electronically to a dispenser (such as a pharmacy) of the patient’s choice. This makes the prescribing and dispensing process more efficient and convenient for patients and staff.</td>
<td><br></td>
</tr>
<tr>
<td>ERS</td>
<td>The NHS e-Referral Service combines electronic booking with a choice of place, date and time for first hospital or clinic appointments. Patients can choose their initial hospital or clinic appointment, book it in the GP surgery at the point of referral, or later at home on the phone or online.
<br>
<br>
This service used to be called Choose and Book.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="F">F</h2></td>
</tr>
<tr>
<td>Federation</td>
<td>For the purposes of federation of appointment bookings through the Appointments API, the federation is simply considered to the list of the organisations which are members of the federation, for example as a list of ODS codes.</td>
<td><br></td>
</tr>
<tr>
<td>FGM</td>
<td>Female Genital Mutilation.</td>
<td><br></td>
</tr>
<tr>
<td>FGM-IS</td>
<td>Female Genital Mutilation Information Sharing.</td>
<td><br></td>
</tr>
<tr>
<td>FHIR</td>
<td>Fast Healthcare Interoperability Resources. A standard for exchanging healthcare information electronically. FHIR (pronounced 'fire') defines a set of resources that represent granular clinical concepts. The resources can be managed in isolation, or aggregated into complex documents.
<br>
<br>
Technically, FHIR is designed for the web. The resources are based on simple XML or JSON structures, with an http-based RESTful protocol where each resource has predictable URL. Where possible, open internet standards are used for data representation.</td>
<td><br></td>
</tr>
<tr>
<td>FHIR® conformance</td>
<td>The FHIR® specification is a "platform specification" - it creates a common platform or foundation on which a variety of different solutions are implemented. As a consequence, this specification usually requires further adaptation to particular contexts of use. FHIR® provides a set of resources that can be used to represent and share the adaptations listed above in a computable fashion. These resources are collectively called the conformance resources.</td>
<td><a href="http://hl7.org/fhir/R4/conformance-module.html" target="_blank">More about FHIR® R4 conformance</a></td>
</tr>
<tr>
<td>FHIR® profiles</td>
<td>HL7 FHIR® UK Core profiles are FHIR assets which are constrained models of FHIR resources, hence making them more suitable for relevant use cases. Further information about FHIR profiling is available.</td>
<td><a href="http://hl7.org/fhir/R4/profiling.html" target="_blank">More about FHIR® R4 profiling</a></td>
</tr>
<tr>
<td><h5 id="G5">FHIR® resources</h5></td>
<td>These are data models of common healthcare entities such as Patient, Practitioner, Organisation, Location, Medication, Condition, Procedure, etc. Such resources could be described as “health IT building blocks” as they can be put together to build working systems which solve real life healthcare problems.</td>
<td><a href="http://hl7.org/fhir/R4/resourcelist.html" target="_blank">More about FHIR® R4 resources</a></td>
</tr>
<tr>
<td><h5 id="G9">FHIR® statuses</h5></td>
<td>HL7 has five descriptive terms that describe the level of stability and implementation readiness associated with different aspects of the specification.</td>
<td><a href="https://www.hl7.org/fhir/versions.html#std-process" target="_blank">More about FHIR® statuses</a></td>
</tr>
<tr>
<td>First of Type</td>
<td>The chosen recipient(s) to test the first deployment of the new capabilities.</td>
<td><br></td>
</tr>
<tr>
<td>FMG</td>
<td>The FHIR Management Group provides day-to-day oversight of FHIR-related work group activities including performing quality analysis, monitoring scope and consistency with FHIR principles and aiding in the resolution of FHIR-related intra and inter-work group issues.</td>
<td><br></td>
</tr>
<tr>
<td>FMM</td>
<td>The FHIR Maturity Model provides a sense of how mature a resource is based on the level and types of review it has been subject to.</td>
<td><br></td>
</tr>
<tr>
<td>FSN</td>
<td>Each concept has one Fully Specified Name (FSN) intended to provide an unambiguous way to name a concept. The purpose of the FSN is to uniquely describe a concept and clarify the meaning. The FSN is not a commonly used term or natural phrase and would not be expected to appear in the human-readable representation of a clinical record.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="G">G</h2></td>
</tr>
<tr>
<td>GDS</td>
<td>Government Digital Service.</td>
<td><br></td>
</tr>
<tr>
<td><h5 id="G1">GitHub</h5></td>
<td>At a high level, GitHub is a website and cloud-based service that helps developers store and manage their code, as well as track and control changes to their code.</td>
<td><a href="https://github.com" target="_blank">More about GitHub</a></td>
</tr>
<tr>
<td>GP Connect</td>
<td>GP Connect allows authorised clinical staff to share and view GP practice clinical information and data between IT systems, quickly and efficiently.</td>
<td><a href="https://digital.nhs.uk/services/gp-connect" target="_blank">More about GP Connect</a></td></tr>
<tr>
<td>GP Connect licence</td>
<td>The terms and conditions for usage of the GP Connect service.</td>
<td><br></td>
</tr>
<tr>
<td>GP2GP</td>
<td>System transferring full GP records between GP systems when patients register with a new GP. Implemented using HL7 v3.</td>
<td><br></td>
</tr>
<tr>
<td>GPES</td>
<td>The General Practice Extraction Service (GPES) collects information for a wide range of purposes, including providing GP payments. It works with the Calculating Quality Reporting Service (CQRS) and GP clinical systems as part of the GP Collections service.</td>
<td><br></td>
</tr>
<tr>
<td>GPET</td>
<td>The General Practice Extraction Tool provides facilities to define, build and execute approved Query Specifications in order to provide data from GP Systems.</td>
<td><br></td>
</tr>
<tr>
<td>GPET-E</td>
<td>The functions delivered by GP System Suppliers to extract data described in Extraction Requirements from Data Provider Systems and send Data Provider Output to GPET-Q in accordance with the GPES-I Interoperability Standard.</td>
<td><br></td>
</tr>
<tr>
<td>GPET-Q</td>
<td>The central system developed by the GPET-Q Contractor to enable the management and scheduling of data extractions by GPET-E systems.</td>
<td><br></td>
</tr>
<tr>
<td>GPSoC contract</td>
<td>The GP System of Choice contract, where a number of suppliers have gained approval to offer services via a centrally controlled contract.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="H">H</h2></td>
</tr>
<tr>
<td>HCP</td>
<td>Health Care Provider refers to a person licensed, certified or otherwise authorized or permitted by law to administer health care in the ordinary course of business or practice of a profession, including a health care facility.</td>
<td><br></td>
</tr>
<tr>
<td>Health and Social Care Network (HSCN)</td>
<td>HSCN is a Wide Area IP Network (WAN) connecting many different sites across the NHS within England & Scotland. It also connects to other networks via gateways, notably to the internet via the internet gateway.</td>
<td><br></td>
</tr>
<tr>
<td>HL7</td>
<td>Health Level Seven HL7, is an all-volunteer, non-profit organization involved in development of international healthcare standards. HL7 is also used to refer to some of the specific standards created by the organization, such as HL7 version 2.x, version 3.0, HL7 Reference Information Model (RIM).</td>
<td><br></td>
</tr>
<tr>
<td><h5 id="G11">HL7 FHIR® standard</h5></td>
<td>FHIR® is a standard for health care data exchange, published by HL7. The version of the HL7 FHIR® UK Core referred to in this standard is FHIR R4.</td>
<td><a href="http://hl7.org/fhir/R4/" target="_blank">More about HL7 FHIR® R4</a></td>
</tr>
<tr>
<td><h5 id="G10">HL7 FHIR® UK Core assets</h5></td>
<td>HL7 FHIR® UK Core assets is a group term for all the things (files/content) that make up an implementation guide. They are all capable of being validated against the FHIR specification.</td><td><br></td>
</tr>
<tr>
<td><h5 id="G3">HL7 International</h5></td>
<td>A not-for-profit, ANSI-accredited standards developing organisation dedicated to providing a comprehensive framework and related standards for the exchange, integration, sharing and retrieval of electronic healthcare information that supports clinical practice and the management, delivery and evaluation of health services.</td>
<td><a href="http://www.hl7.org/" target="_blank">More about HL7 International</a></td>
</tr>
<tr>
<td><h5 id="G4">HL7 UK</h5></td>
<td>HL7 UK looks after HL7 International standards developing activities in the UK.</td>
<td><a href="https://www.hl7.org.uk/" target="_blank">More about HL7 UK</a></td>
</tr>
<tr>
<td>HO</td>
<td>Home Office.
</td>
<td><br></td>
</tr>
<tr>
<td>HSCI</td>
<td>Health and Social Care Integration. This integrates local health and social care services to improve coordination between local health and social care agencies, leading to improved experiences for people using these services.</td>
<td><br></td>
</tr>
<tr>
<td>HTML</td>
<td>Hyper Text Mark-up Language. HTML is not a programming language, it is a markup language. A mark-up language is a set of mark-up tags. HTML uses mark-up tags to describe web pages.</td>
<td><br></td>
</tr>
<tr>
<td>HTTP</td>
<td>Hyper Text Transfer Protocol is the primary data transfer protocol used for web content and REST APIs.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="I">I</h2></td>
</tr>
<tr>
<td>ICS</td>
<td><a href="https://www.england.nhs.uk/integratedcare/what-is-integrated-care/">Integrated Care Systems (ICSs)</a>, which grew out of Sustainability and Transformation Partnerships (STPs) replaced <a href="https://webarchive.nationalarchives.gov.uk/ukgwa/20220613043745/https://www.england.nhs.uk/commissioning/who-commissions-nhs-services/ccgs/">Clinical Commissioning Groups (CCGs)</a> in April 2022. ICSs fund NHS care providers at a local level. This change is intended to bring together healthcare providers, commissioners and local authorities at a local level to improve the level of integrated care</td>
<td><br></td>
</tr>
<tr>
<td>IDT</td>
<td>Although initially used as an adjunct to support effective training, the Intelligent Data Toolkit has been enhanced to support content changes in the clinical system and to enable cost effective commissioning in localities.</td>
<td><br></td>
</tr>
<tr>
<td>IHS</td>
<td>Immigration Health Surcharge.</td>
<td><br></td>
</tr>
<tr>
<td><h5 id="G13">Implementation Guide (IG)</h5></td>
<td>An implementation guide is a set of rules about how HL7 FHIR® resources are used (or should be used) to solve a particular problem, with associated documentation to support and clarify the usage.</td>
<td><br></td>
</tr>
<tr>
<td><h5 id="implimentationGuideDigiMeds">Implementation Guide for Digital Medicines</h5></td>
<td>NHS Guidance on sharing medicines data between clinical systems and between integrated and shared record systems across the UK health sector.</td>
<td><a href="https://simplifier.net/guide/uk-core-implementation-guidance-directory?version=current">More information</a></td>
</tr>
<tr>
<td>Independent Group Advising on the Release of Data (IGARD)</td>
<td>Independent Group Advising on the Release of Data (IGARD) is an advisory body to the NHS England Board, aiming to improve transparency, accountability, quality and consistency through robust, independent scrutiny of NHS England data distributions, as well as providing a voice for the public. 
<br><br>
IGARD also makes general recommendations or observations to NHS England about their processes, policies and procedures, including transparency measures such as registers.</td>
<td><br></td>
</tr>
<tr>
<td>Information Asset Owner (IAO)</td>
<td>The Information Asset Owner (IAO) will be a senior member of staff who is the nominated owner for one or more identified information assets of the organisation. IAOs will support the organisation's Senior Information Risk Owner (SIRO) in their overall information risk management function as defined in the organisation's policy. </td>
<td><br></td>
</tr>
<tr>
<td>Information Governance (IG)</td>
<td>Information Governance (IG) is the framework for handling information in a secure and confidential manner that allows organisations and individuals to manage patient, personal and sensitive information legally, securely, efficiently and effectively in order to deliver the best possible healthcare and services.
<br><br>
IG applies to, and impacts on, everyone working for, or on behalf of, the NHS. Additionally, everyone working in the NHS has a legal duty to keep information about others secure and confidential.</td>
<td><br></td>
</tr>
<tr>
<td>Information Security Management System (ISMS)</td>
<td>An information security management system (ISMS) is a set of policies and procedures for systematically managing an organization's sensitive data. The goal of an ISMS is to minimize risk and ensure business continuity by proactively limiting the impact of a security breach.
<br><br>
An ISMS typically addresses employee behaviour and processes as well as data and technology. It can be targeted toward a particular type of data, such as customer data, or it can be implemented in a comprehensive way that becomes part of the company's culture.</td>
<td><br></td>
</tr>
<tr>
<td><h5 id="G7">INTEROPen</h5></td>
<td>INTEROPen is an OPEN collaboration of individuals, industry, standards organisations and health and care providers, who have agreed to work together to accelerate the development of open standards for interoperability in the health and social care sector.</td>
<td><br></td>
</tr>
<tr>
<td>Invalidated patients</td>
<td>Some patient records are marked as invalidated in PDS - also known as 'redacted' in FHIR terminology.
<br><br>
Invalidated patient records are not returned in search results. If an invalidated patient record has been superseded, the superseding record is returned instead.</td>
<td><br></td>
</tr>
<tr>
<td>ITK</td>
<td>The Interoperability Toolkit, in the context of the NHS this is a set of common specifications, frameworks and implementation guides to support interoperability within local organisations and across local health and social care communities. The ITK is not a piece of software, it is not a product which is downloadable from this website.
<br><br>
ITK Conformance is the NHS England team that manages the Technical Conformance of a Product as part of the Solution Assurance function.</td>
<td><br></td>
</tr>
<tr>
<td>ITS</td>
<td>Implementation Technology Specification. The ITS defines how to represent an HL7 message in a serial form that can be transmitted from a sender to a receiver.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="J">J</h2></td>
</tr>
<tr>
<td>JSON</td>
<td>Javascript Object Notation is a lightweight data-interchange format. It is easy for humans to read and write and easy for machines to parse and generate. It is based on a subset of the JavaScript Programming Language.</td>
<td><br></td>
</tr>
<tr>
<td>JWT</td>
<td>JSON Web Token is a JSON-based open standard (RFC 7519) for creating access tokens that assert a number of claims, typically used to transmit user identity information and other attributes about a user, system or device.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="L">L</h2></td>
</tr>
<tr>
<td>LDAP</td>
<td>Light-weight Directory Access Protocol is an open, vendor-neutral, industry-standard application protocol for accessing and maintaining distributed directory information services over an Internet Protocol (IP) network.</td>
<td><br></td>
</tr>
<tr>
<td>Local patient database</td>
<td>Applications might cache the results of recent patient data searches in a local patient database (or index). This can create a data quality problem later, if the application does not check that the data it holds is still the most up to date version.
<br><br>
For example, for PDS an application must ensure it uses up to date data by synchronising any local patient database with PDS. (This does not apply to data that is not held in PDS.) 
<br><br>
If the patient cannot confirm the correct record, it must be referred to a back office function for resolution. </td>
<td><br></td>
</tr>
<tr>
<td>Local system</td>
<td>Local systems are those such as GP systems, hospital systems or ambulance service systems. Typically these talk to national central systems such as the Personal Demographics Service or the Summary Care Record. Sometimes they talk to other local systems directly using API standards, or they might talk to other local systems through intermediaries such as a proxy (for a synchronous API) or a message broker (for an asynchronous API).</td>
<td><br></td>
</tr>
<tr>
<td>LRS</td>
<td>Legitimate Relationship Service. A Legitimate Relationship is a relationship between a clinician (or NHS organisation work group) and a patient, that gives the clinician, or work group member, certain levels of entitlement to access that patient’s health record maintained on national systems.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="M">M</h2></td>
</tr>
<tr>
<td>Medicines and Healthcare Products Regulatory Agency (MHRA)</td>
<td>The Medicines and Healthcare products Regulatory Agency regulates medicines, medical devices and blood components for transfusion in the UK.
<br><br>
MHRA is an executive agency, sponsored by the Department of Health and Social Care.</td>
<td><br></td>
</tr>
<tr>
<td>MESH</td>
<td>Messaging Exchange for Social Care is the main asynchronous messaging service used across health and social care. It works on the Spine infrastructure, and is used to transfer electronic messages directly from one application to another, so different organisations can communicate securely. As an example, pathology labs use MESH to communicate test results to GP practices.
<br><br>
MESH replaced the Data Transfer Service (DTS).</td>
<td><br></td>
</tr>
<tr>
<td>Message broker</td>
<td>Computer systems send messages via an intermediary known as a proxy (for synchronous APIs) or a message broker (for asynchronous APIs). Some message brokers deliver the message on to the recipient, like a postal van. Other message brokers require the recipient to check for messages, like a post office box.</td>
<td><br></td>
</tr>
<tr>
<td>MHS</td>
<td>Message Handling System is a name used to refer to the messaging capabilities of systems sending and receiving messages from Spine.
</td>
<td><br></td>
</tr>
<tr>
<td>MIF</td>
<td>Model Interchange Format is a set of XML formats used to support the storage and exchange of HL7 version 3 artefacts. It is the pre-publication format of HL7 v3 artefacts used by tooling. It's also the formal definition of the HL7 metamodel.
<br><br>
The MIF can be transformed into derived forms such as Unified Modelling Language (UML) /XML Metadata Interchange (XMI) or Web Ontology Language (OWL).</td>
<td><br></td>
</tr>
<tr>
<td>MIG</td>
<td>The Medical Interoperability Gateway is a supplier lead interoperability solution provided by EMIS + Vision which allows third parties access to GP data.</td>
<td><br></td>
</tr>
<tr>
<td>MIM</td>
<td>The Message Implementation Manual describes the HL7 messages used for communications across the NPfIT programme.
<br><br>
Not all messages are HL7v3.
<br><br>
Not all messages are in the MIM.</td>
<td><br></td>
</tr>
<tr>
<td>MPM</td>
<td>Multi-Payload Message format for carrying a combination of CDA and non CDA HL7 messages, linked by a common Control Act in the payload.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="N">N</h2></td>
</tr>
<tr>
<td>N3</td>
<td>Now replaced by the Health and Social Care Network (HSCN).</td>
<td><br></td>
</tr>
<tr>
<td>NACS</td>
<td>National Administrative Codes Service. The service previously known as the National Administrative Codes Service (NACS) is now known as the Organisation Data Service (ODS). It was responsible for the publication of organisation and practitioner codes, and for the national policy and standards with regard to the majority of organisation codes. These code standards form part of the NHS data standards.</td>
<td><br></td>
</tr>
<tr>
<td>National Events Management Service (NEMS)</td>
<td>The National Events Management Service (NEMS) enables the sharing of specific health information about a patient in near real-time. Information is shared in the form of event messages, following a publish and subscribe model and using the <a href="https://digital.nhs.uk/services/spine">NHS Spine</a>.</td>
<td><br></td>
</tr>
<tr>
<td>NHS CfH</td>
<td>NHS Connecting for Health was an agency of the Department of Health. This organization was delivering the National Programme for Information Technology (NPfIT) in the NHS. Since 1 April 2013 substantive functions of this organization are transferred to NHS England.</td>
<td><br></td>
</tr>
<tr>
<td>NHS CRS</td>
<td>The NHS Care Records Service (NHS CRS) is a secure service to improve the way health information is stored and shared in the NHS in England. It is linking health information from different parts of the NHS to support the NHS in delivering better, safer care.</td>
<td><br></td>
</tr>
<tr>
<td>NHSD</td>
<td>NHS Digital, formerly known as the Health and Social Care Information Centre (HSCIC). Merged with NHS England on 1st Feb 2023. </td>
<td><br></td>
</tr>
<tr>
<td><h5 id="NHSD_DMD">NHS Data Model and Dictionary</h5></td>
<td>The NHS Data Model and Dictionary gives a reference point for assured information standards, to support health care activities in the NHS in England. The NHS Data Model and Dictionary has been developed for everyone who is actively involved in the collection of data and the management of information in the NHS. The NHS Data Model and Dictionary Service provides the development, maintenance and support of NHS Information Standards.</td>
<td><a href="https://www.datadictionary.nhs.uk/index.html" target="_blank">More about the NHS Data Model and Dictionary</a></td>
</tr>
<tr>
<td>NHS Data Strategy</td>
<td>The NHS Data Strategy sets out the Secretary of State for Health and Social Care’s vision for how data will be used to improve the health and care of the population in a safe, trusted and transparent way.</td>
<td><a href="https://www.gov.uk/government/publications/data-saves-lives-reshaping-health-and-social-care-with-data" target="_blank">More about the NHS Data Strategy (2022)</a></td>
</tr>
<tr>
<td><h5 id="NHSD_PDS">NHS England Personal Demographics Service FHIR API</h5></td>
<td>Access the Personal Demographics Service (PDS) - the national electronic database of NHS patient details such as name, address, date of birth, related people, registered GP and NHS number.</td>
<td><a href="https://digital.nhs.uk/developer/api-catalogue/personal-demographics-service-fhir">More about the NHS England Personal Demographics Service</a></td>
</tr>
<tr>
<td>NHS Scotland Data Dictionary</td>
<td>The Scotland Data Dictionary managed by PHS, and is a guide to the definitions and data standards, and SMR datasets.</td>
<td><a href="https://www.ndc.scot.nhs.uk/Data-Dictionary/" target="_blank">More about the NHS Scotland Data Dictionary</a></td>
</tr>
<tr>
<td><h5 id="G15">NHS Wales Data Dictionary</h5></td>
<td>The Welsh Data Dictionary is a guide to the definitions, collection and interpretation of nationally agreed data standards adopted by the NHS in Wales. It has been prepared for the use of everyone who is actively involved in the collection of data and the use of information in NHS Wales.</td>
<td><a href="https://www.datadictionary.wales.nhs.uk" target="_blank">More about the NHS Wales Data Dictionary</a></td>
</tr>
<tr>
<td>NPfIT</td>
<td>National Programme for IT. A key aim of the National Programme is to give healthcare professionals access to patient information safely, securely and easily, whenever and wherever it is needed.</td>
<td><br></td>
</tr>
<tr>
<td>NRLS</td>
<td>National Record Locator Service is a technical proof of concept acting as a national index to identify available records for patients and locate them across local and national care record solutions (such as SCR).</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="O">O</h2></td>
</tr>
<tr>
<td>ODS</td>
<td>The Organisation Data Service is responsible for publishing organisation and practitioner codes, along with related national policies and standards. They’re also responsible for the ongoing maintenance of the organisation and person nodes of the Spine Directory Service, the central data repository used within various NHS systems and services.
<br>
<br>
These code standards form part of the NHS data standards.
<br>
<br>
This was previously known as National Administrative Codes Service (NACS).</td>
<td><br></td>
</tr>
<tr>
<td>OID</td>
<td>Object Identifier is a unique identifier. It can be used to identify coding systems.</td>
<td><br></td>
</tr>
<tr>
<td>On the wire (instance format)</td>
<td>The format of the xml instance that actually flows over the network between systems.</td>
<td><br></td>
</tr>
<tr>
<td>OVM</td>
<td>Overseas Visitors Manager.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="P">P</h2></td>
</tr>
<tr>
<td>Participation</td>
<td>The involvement of a HL7 role class in an HL7 act class.</td>
<td><br></td>
</tr>
<tr>
<td>PAS</td>
<td>The Patient Administration System is a core component of a hospital computer system which records the patient’s name, home address, date of birth and each contact with the outpatient department or admission and discharge.
<br>
<br>
The NHS patient’s record and appointment tracking system is often called PAS, depending on the NHS Hospital Trust. This computerised administration solution that assists with planning, tracking and recording the patient’s contact with the outpatient department or admission and discharge.</td>
<td><br></td>
</tr>
<tr>
<td>PCT</td>
<td>Primary Care Trust. Responsible for primary and community health services within a geographical boundary.</td>
<td><br></td>
</tr>
<tr>
<td>PDS</td>
<td>The Personal Demographics Service (PDS) is the national electronic database of NHS patient details such as name, address, date of birth and NHS number (known as demographic information) and medical information.</td>
<td><br></td>
</tr>
<tr>
<td>PID</td>
<td>The HL7 Patient Identification segment is found in every type of ADT message (i.e. ADT-A01, ADT-A08, etc.) and contains 30 different fields with values ranging from patient ID number, to patient sex, to address, to marital status, to citizenship. The PID segment provides important identification information about the patient and, in fact, is used as the primary means of communicating the identifying and demographic information about a patient between systems.</td>
<td><br></td>
</tr>
<tr>
<td>PNG</td>
<td>Portable Network Graphics is a bit-mapped image format and video codec that employs lossless data compression. PNG was created to improve upon and replace GIF (Graphics Interchange Format) as an image-file format not requiring a patent license.</td>
<td><br></td>
</tr>
<tr>
<td>Principal supplier</td>
<td>The name given to a group of suppliers who provide GPs with the core system available under the GPSoC contract.</td>
<td><br></td>
</tr>
<tr>
<td>Product</td>
<td>The software application built to interface with an NHS England API.</td>
<td><br></td>
</tr>
<tr>
<td>Provider</td>
<td>An individual or an organisation that provides health care for a patient. Also a system which provides data by exposing Open APIs.</td>
<td><br></td>
</tr><tr>
<td>Proxy server</td>
<td>A server that acts as an intermediary for requests from clients seeking resources from other servers.</td>
<td><br></td>
</tr>
<tr>
<td>PRSB</td>
<td>Professional Record Standards Body. The independent PRSB is the first point of call for care professionals, service providers, commissioners, policy makers, professional bodies and system suppliers for expertise and all matters relating to care records.
<br><br>
The PRSB is a national body providing an independent patient and professional voice on health informatics issues, to ensure that professionally endorsed standards are adopted to enable safe and effective information sharing and exchange.</td>
<td><br></td>
</tr>
<tr>
<td>PSIS</td>
<td>Personal Spine Information Service. The central database on the Spine containing clinical records for each NHS patient.</td>
<td><br></td>
</tr>
<tr>
<td>PT</td>
<td>Preferred term. Each concept has one preferred term in a given language dialect. The preferred term is a common word or phrase used by clinicians to name that concept.</td>
<td><br></td>
</tr>
<tr>
<td>PTL</td>
<td>Path To Live.</td>
<td><br></td>
</tr>
<tr>
<td>PTV</td>
<td>The Permission to View (PTV) is a business service that records that a patient has given an explicit permission to view their SCR.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="R">R</h2></td>
</tr>
<tr>
<td>RBAC</td>
<td>RBAC is the process through which a national set of job roles, activities and work-groups can be applied to grant users access to functionality and indirectly to data within NHS national (Spine) services. Role Based Access Control defines roles and allows business activities associated with a user (via their smartcard). It is Implemented using SAML.</td>
<td><br></td>
</tr>
<tr>
<td>Requester</td>
<td>An individual or an organisation responsible for the requesting an action to be performed for the patient.</td>
<td><br></td>
</tr>
<tr>
<td>REST</td>
<td>Representational State Transfer is a protocol based upon a network of web resources (a virtual state-machine) where the user progresses through the application by selecting links, such as /user/tom, and operations such as GET or DELETE (state transitions), resulting in the next resource (representing the next state of the application) being transferred to the user for their use.
<br><br>
It is typically preferred due to it being stateless, so no information about the client session needs to be maintained on the server.</td>
<td><br></td>
</tr>
<tr>
<td>RESTful</td>
<td>Interfaces are often referred to as being “RESTful” when they follow principles of “REST” to avoid debate about whether they conform to “REST”.</td>
<td><br></td>
</tr>
<tr>
<td>RIM</td>
<td>The Reference Information Model is the cornerstone of the HL7 Version 3 development process. An object model created as part of the Version 3 methodology, the RIM is a large, pictorial representation of the HL7 clinical data (domains) and identifies the life cycle that a message or groups of related messages will carry.
<br><br>
It is a shared model between all domains and is the model from which all domains create their messages.</td>
<td><br></td>
</tr>
<tr>
<td>RMIM</td>
<td>Refined Message Information Model (RMIM) is a HL7 model derived from the HL7 Reference Information Model (RIM).</td>
<td><br></td>
</tr>
<tr>
<td>ROA</td>
<td>Resource-oriented architecture is a style of software architecture and programming paradigm for designing and developing software in the form of resources with “RESTful” interfaces.</td>
<td><br></td>
</tr>
<tr>
<td>Role</td>
<td>A class in HL7 that describes a responsibility or part played by an entity.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="S">S</h2></td>
</tr>
<tr>
<td>SAML</td>
<td>Security Assertion Markup Language is an open standard for exchanging authentication and authorisation data between parties.</td>
<td><br></td>
</tr>
<tr>
<td>Schematron</td>
<td>The schematron is an XML structure validation language for making assertions about the presence or absence of patterns in trees. It is a simple and powerful structural schema language.</td>
<td><br></td>
</tr>
<tr>
<td>SCR (SCRa)</td>
<td>Summary Care Record. The SCR is intended to support patient care in urgent and emergency care settings. The SCR stores a defined set of key patient data for every patient in England except those who elect not to have one. This data provides a summary record created from information held on GP clinical systems. This summary record helps to ensure a continuity of care across a variety of care settings.
<br><br>
SCRa is an end user application used to access SCRs.</td>
<td><br></td>
</tr>
<tr>
<td>SDS</td>
<td>The NHS Spine Directory Service is a component of the NHS Spine service, comprising of the Spine User Directory and Spine Accredited Systems and Services. The SDS ensures that transactions/messages are only processed from authorised users and systems (implemented with LDAP). The Spine Directory Service also stores a record of each NHS organisation.</td>
<td><br></td>
</tr>
<tr>
<td>Secondary Uses Service (SUS)</td>
<td>The Secondary Uses Service (SUS) is the single, comprehensive repository for healthcare data in England which enables a range of reporting and analyses to support the NHS in the delivery of healthcare services.</td>
<td><br></td>
</tr>
<tr>
<td>Senior Information Risk Owner (SIRO)</td>
<td>A Senior Information Risk Owner (SIRO) is an Executive Director or member of the Senior Management Board of an organisation with overall responsibility for an organisation's information risk policy.
<br><br>
The SIRO is accountable and responsible for information risk across the organisation. They ensure that everyone is aware of their personal responsibility to exercise good judgement, and to safeguard and share information appropriately.</td>
<td><br></td>
</tr>
<tr>
<td>Senior Responsible Owner (SRO)</td>
<td>The senior responsible owner (SRO) is accountable for ensuring a programme or project meets its objectives, delivers the projected outcomes and realises the required benefits.</td>
<td><br></td>
</tr>
<tr>
<td>Sensitive patients</td>
<td>Some patients are known as sensitive (or restricted) in PDS. 
<br><br>
To protect the location of these patients, who might be at risk, we restrict access to some data in their records.
<br><br>
The purpose is to ensure that patient information that might imply their location is protected from viewing by any PDS user, other than the authorised staff in the PDS National Back Office (NBO) who have responsibility for managing restricted records. </td>
<td><br></td>
</tr>
<tr>
<td>Service user</td>
<td>A person who uses or is eligible to use a health care or social care service.</td>
<td><br></td>
</tr>
<tr>
<td>SMSP</td>
<td>Spine Mini Service Provider. SMTP is middle ware that provides access to lightweight, filtered services on national applications.</td>
<td><br></td>
</tr>
<tr>
<td><h5 id="G2">Simplifier</h5></td>
<td>Simplifier is an online collaboration platform, used for the authoring and publishing of FHIR data models.</td>
<td><a href="https://simplifier.net/about" target="_blank">Simplifier overview</a><br><a href="https://simplifier.net/features?plan=enterprise" target="_blank">Features of Simplifier</a></td>
</tr>
<tr>
<td><h5 id="G16">SNOMED CT</h5></td>
<td>SNOMED CT is a structured clinical vocabulary for use in an electronic health record.</td>
<td><a href="https://digital.nhs.uk/services/terminology-and-classifications/snomed-ct" target="_blank">More about SNOMED CT</a></td>
</tr>
<tr>
<td><h5 id="G17">SNOMED CT Expression Constraint Language (ECL)</h5></td>
<td>SNOMED CT Expression Constraint Language (ECL) is a formal syntax for representing SNOMED CT expression constraints.</td>
<td><a href="https://confluence.ihtsdotools.org/display/DOCECL" target="_blank">More about SNOMED CT ECL</a></td>
</tr>
<tr>
<td>SOA</td>
<td>Method for systems integration and development that allows different applications to exchange data in a loosely coupled way.</td>
<td><br></td>
</tr>
<tr>
<td>SOAP</td>
<td>A protocol specification for exchanging structured information in the implementation of web services. SOAP allows processes running on disparate operating systems (such as Windows and Linux) to communicate using Extensible Markup Language (XML). Since web protocols like HTTP are installed and running on all operating systems, SOAP allows clients to invoke web services and receive responses independent of language and platforms.</td>
<td><br></td>
</tr>
<tr>
<td>Solution Assurance (SA)
</td>
<td>Solution Assurance is a technical assurance function within NHS England, providing expertise to enable national programmes and health and social care organisations to develop effective systems, information and technology. SA contributes to safer treatment and better care within health and social care services in England.
<br><br>
Assurance is the process by which we ensure that healthcare IT systems meet their functional requirements and integrate effectively with other systems and services. SA makes sure it does what it's supposed to do, when it's needed, and that any associated risks are mitigated appropriately. We focus on understanding and improving the quality of service provided by a solution and this is achieved by targeting very specific technical, operational or safety risks.
<br><br>
By solution we mean the overall end product or service, which can involve looking at software, hardware or a number of additional factors including how humans interact with the solutions.</td>
<td><br></td>
</tr>
<tr>
<td>Spine</td>
<td>Spine is a collection of national applications, services and directories which support the health and social care sector in the exchange of information in national and local IT systems. A national, central service that underpins the NHS Care Records Service.
<br><br>
It manages the patient’s national Summary Care Records. Clinical information is held in the Personal Spine Information Service (PSIS) and demographic information is held in the Personal Demographics Service (PDS). The Spine also supports other systems and services such as the e-Referral Service and the Electronic Prescription Service.</td>
<td><br></td>
</tr>
<tr>
<td><h5 id="spine">Spine Directory Service</h5></td>
<td>Access accredited system information and messaging endpoint details in the Spine Directory Service (SDS) using our FHIR-conformant API.</td>
<td><a href="https://digital.nhs.uk/developer/api-catalogue/spine-directory-service-fhir">More information about SDS</a></td>
</tr>
<tr>
<td>Spine Mini Service (SMS)
</td>
<td>The Spine Mini Service enables systems to get information from Spine. Connecting an IT system directly to the national Spine requires a secure NHS connection and appropriate levels of compliance with information governance processes. The Spine Mini Service allows secure read-only connections to some national NHS services, meaning:
<br><br>
<li>Health and social care organisations can access some types of patient information more easily</li>
<br>
<li>Developers can integrate their systems with Spine more easily, reducing barriers to entry for health and care system development</li></td>
<td><br></td>
</tr>
<tr>
<td>SSB</td>
<td>Spine Security Broker is a system within the Spine used for managing smartcard authentication.</td>
<td><br></td>
</tr>
<tr>
<td>SSP</td>
<td>Spine Secure Proxy is a system within the Spine used to securely broker API calls between external systems.</td>
<td><br></td>
</tr>
<tr>
<td>STU</td>
<td>Standard for Trial Use. The original DSTU2 FHIR standard has been superseded by the new standard STU3 to reflect that important parts of the spec are well past the draft stage.</td>
<td><br></td>
</tr>
<tr>
<td>Superseded patients</td>
<td>Some patient records are marked as superseded in PDS. This means that for some reason an original record for an NHS number is no longer valid and has been replaced with a new record and NHS number. In this case, PDS returns details of the new record and NHS number.
<br><br>
For example, a baby assigned an NHS number at birth that relates to the wrong mother, will have its NHS number and record invalidated and superseded by new ones that relate to the correct mother.</td>
<td><br></td>
</tr>
<tr>
<td>Supplier Conformance Assessment List</td>
<td>The Supplier Conformance Assessment List (SCAL) is a spreadsheet that forms the basis of the onboarding process used by many of the more recent NHS England APIs. For each software being onboarded, a SCAL document is produced by NHS England based on the developer's details and the APIs the software interfaces with, and the SCAL document is supplied to the developer early in the <a href="https://digital.nhs.uk/developer/guides-and-documentation/onboarding-process">developer onboarding process.</a></td>
<td><br></td>
</tr>
<tr>
<td>Synonym</td>
<td>A synonym represents a clinical or pharmaceutical term, other than the Fully Specified Name (FSN) or Preferred Term, that can be used to represent a concept in a particular language or dialect.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="T">T</h2></td>
</tr>
<tr>
<td>Template</td>
<td>A template is a HL7 Refined Message Information Model which is used to constrain another HL7 model.</td>
<td><br></td>
</tr>
<tr>
<td>Templated (instance format)</td>
<td>The format of the xml instance that has been transformed from 'on the wire' format to a conformance format to enable more rigorous testing.</td>
<td><br></td>
</tr>
<tr>
<td>TMS</td>
<td>The Transaction Messaging Service (TMS) is a message transfer service that allows clinical messages from NHS Care Records Service (NHS CRS) users to be securely routed to the service they are requesting and to manage the response to that request. Depending on the type of message (such as relating to the e-Referral Service or the Personal Demographics Service), the Transaction Messaging Service identifies where the message needs to be sent.</td>
<td><br></td>
</tr>
<tr>
<td>TOM</td>
<td>The Target Operating Model (TOM) process for onboarding third party software is simpler than the traditional CAP. Its replacement is the SCAL process, and more recently the Digital Onboarding Service</td>
<td><br></td>
</tr>
<tr>
<td>TRUD</td>
<td>The Terminology Reference Update Distribution Service (TRUD) provides a mechanism for the UK Terminology Centre to license and distribute reference-data to interested parties.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="U">U</h2></td>
</tr>
<tr>
<td><h5 id="UCUM">UCUM</h5></td>
<td>Unified Code for Units of Measure (UCUM) is a code system intended to include all units of measures being contemporarily used in international science, engineering, and business.</td>
<td><a href="https://ucum.org/" target="_blank">UCUM website</a></td>
</tr>
<tr>
<td>UML</td>
<td>The Unified Modelling Language is a family of graphical notations baked by a single meta-model, that help in designing and describing software systems. Especially useful when working with OOP paradigms.</td>
<td><br></td>
</tr>
<tr>
<td>UMS</td>
<td>Unattended Messaging Session is when a system sends a message with no user intervention, and with no authenticated user session. Examples of this might be a Patient Administration System (PAS) requesting PDS retrievals as part of populating the day’s patient list.</td>
<td><br></td>
</tr>
<tr>
<td>URL</td>
<td>Uniform Resource Locator is a reference (an address) to a resource on the internet. For example, a URL could be the name of a file because most URLs refer to a file on some machine on the network. However, URLs also can point to other resources on the network, such as database queries and command output.</td>
<td><br></td>
</tr>
<tr>
<td>URP</td>
<td>A User Role Profile is the information about the clinical role an authenticated user is authorised to perform.</td>
<td><br></td>
</tr>
<tr>
<td><h5 id="USCore">US Core</h5></td>
<td>The US Core is based on FHIR® Version R4 and its Implementation Guide defines the minimum set of constraints on the FHIR resources to create the US Core Profiles. It also defines the minimum set of FHIR® RESTful interactions for each of the US Core Profiles to access patient data.</td>
<td><a href="http://www.hl7.org/fhir/us/core/" target="_blank">US Core website</a></td>
</tr>
<tr>
<td>Use case</td>
<td>A usage scenario for a software application, often used to explain the user's possible interactions with it. It might be shown by a swim lane diagram showing the interactions, for instance, between end users, the application and the endpoints of an API.
<br><br>
For example, as part of a healthcare worker providing direct healthcare to a patient, they use an application to access PDS (via an API) to get the patient's details based on their NHS number.</td>
<td><br></td>
</tr>
<tr>
<td>Use case diagram</td>
<td>A graphical depiction of a user's possible interactions with a system, perhaps presented as a swim lane diagram, or in Universal Modelling Language (UML).</td>
<td><br></td>
</tr>
<tr>
<td>UUID</td>
<td>A Universally Unique Identifier is a 128-bit label used to identify information in computer systems.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="V">V</h2></td>
</tr>
<tr>
<td>Validated NHS number</td>
<td>A valid NHS number is one that has the correct format and passes the number check digit calculation.</td>
<td><br></td>
</tr>
<tr>
<td>Verified NHS number</td>
<td>A verified NHS number is one where the patient’s identity has been cross-checked using demographic details on the Personal Demographics Service (PDS).</td>
<td><br></td>
</tr>
<tr>
<td>VNA</td>
<td>A Vendor Neutral Archive is medical imaging technology in which images and documents (and potentially any file of clinical relevance) are stored (archived) in a standard format with a standard interface, such that they can be accessed in a vendor-neutral manner by other systems.</td>
<td><br></td>
</tr>
</table>

<br><br>
<table class="assets">
<tr>
<th width="20%">Term</th>
<th width="60%">Definition</th>
<th width="20%">Further Reading</th>
</tr>
<tr>
<td colspan="3"><h2 id="X">X</h2></td>
</tr>
<tr>
<td>x_domain</td>
<td>A HL7 term for a subset of a HL7 vocabulary code list.</td>
<td><br></td>
</tr>
<tr>
<td>XML</td>
<td>eXtensible markup language is a protocol designed to store and transport data. XML was designed to be both human and machine readable.</td>
<td><br></td>
</tr>
<tr>
<td>xPath</td>
<td>XPath is a major element in the XSLT standard and can be used to navigate through elements and attributes in an XML document. XPath is a syntax for defining parts of an XML document and uses path expressions to navigate in XML documents. It contains a library of standard functions.</td>
<td><br></td>
</tr>
<tr>
<td>XSLT</td>
<td>Transform. A language for transforming extensible mark-up language.</td>
<td><br></td>
</tr>
</table>
