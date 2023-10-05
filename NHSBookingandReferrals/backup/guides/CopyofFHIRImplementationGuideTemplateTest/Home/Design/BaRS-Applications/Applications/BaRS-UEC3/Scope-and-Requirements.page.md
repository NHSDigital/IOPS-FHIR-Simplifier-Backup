---
topic: APP3-ScopeAndRequirements
---

 <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This Application is currently under development <hr><p> This is a preview of a developing documentation for information only. It is not intended to be used until the completed v1.0.0 Application is released<p> If you are interested in developing a BaRS compliant solution for these use cases right now, please use the contact form <a href="https://digital.nhs.uk/services/booking-and-referral-standard/enquiry-form" target="_blank">here</a> and the team will be in touch</div>


## {{page-title}}

### Scope Overview

This BaRS Application (application 3) covers only use cases:
* Referral Requests for 999 ASTs to CAS


The payloads and workflow have been designed to support these services. Other {{pagelink:applications, text:BaRS Applications}} offer scope for alternative use cases.

### Functional Scope

**Service Discovery**
?????

**Referral Request**
??????

**Cancel Referral Request**
??????

**API-M**
* All requests and response associated with BaRS must occur through the BaRS API Proxy

**Constraints**
???????

### Requirements

**Service Discovery** 
??????

**Referral Request**
??????

**Understanding Timings**
??????

**Flags**
??????

**Contacts** 
* A minimum of one contact (patient or third party) with a contact method (phone, email, etc.) of phone **must** be provided in requests
* All contacts **must** have a rank
* There **must** be only one contact with a rank of 1
* All contacts **must** have at least one contact method (phone, email, etc.)
* All contact methods **must** have a rank
* There **must** be only one contact method with a rank of 1
* The contact ranked 1 and the contact method ranked 1 **must** be the primary callback for the request
<br>
<br>
### Audit
* Sufficient information around any activity through the API and subsequent BaRS workflow **must** be persisted to aid support incidents and audit requirements
<br>
<br>
### Error Handling 
* Suppliers **must** adhere to the {{pagelink:Home/Design/BaRS-Core/Error-Handling.page.md, text:error handling guidance}} 
<br>
<br>
### Non Functional 
* Suppliers **must** adhere to the {{pagelink:Home/Design/BaRS-Core/Non-functional-requirements.page.md, text:non functional requirements}}
<br>
<br>
<hr>