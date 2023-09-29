## The SCR is an electronic record of important patient information, created from GP medical records. It can be seen and used by authorised staff in other areas of the health and care system involved in the patient's direct care.

The primary means by which the SCR is updated is the "GP Summary Upload".  When certain data items are changed in the GP patient record, these changes are "pushed" to the central SCR repository via the GP Summary upload

The core elements of this upload are:
* Medicines you are taking
* Allergies you suffer from
* Any bad reactions to medicines. (“adverse reactions”)

Therefore, when a change is made to the patient’s GP Practice record, it triggers a replacement Summary Care Record document to be sent to spine. This latest summary can then be seen by suitable authorised staff using a number of means, primarily via the Summary Care Record Application (SCRA)

The SCR API will meet the requirements of the MVP which has been agreed between GP IT and the SCR programme. 

The MVP is defined as follows:
* In scope: SCR Additional information as defined in SCR v2.1
* Out of scope: Any requirements around processing structured medical information contained within GP Summary Upload, except for a defined set of Covid-19 SNOMED CT codes.
* In scope: Integration with ACS (access control service) to Record Dissent from SCR, and query dissent from SCR.
* In scope: Spine interactions to enable new entrant system to view SCR within their UI.
* In scope: Spine interactions to enable upload of GP Summary (REPC_IN150016UK05 interaction).
* Out of scope: Withdraw GP Summary and Initial GP Summary Upload.
* In scope: Reading Initial GP Summary.
* Out of scope: Preparation of the XHTML content included in the GP Summary. This will be the responsibility of the new entrant supplier system.

The MVP API will be used by GP foundation systems to push information to the central SCR repository upon patient clinical events. These events are essentially where certain data elements the patient's care record at the practice are changed.