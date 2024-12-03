## Introduction

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This Implementation Guide is for internal use only</div>

The Patient Audit Record Service (PARS) has been developed to record and manage audit events related to patient data acess. By tracking and monitoring how and when patient data is accessed, it meets the requirement to maintain accountability, transparency and traceability in the handling of patient information.

<b> This guide focuses on one Use Case: Recording Audit Events for Patient Data Access </b>

PARS supports the logging of actions taken on patient records, such as viewing, updating, or sharing data using the FHIR AuditEvent resource. This ensures that organisations can maintain a detailed audit trail for compliance with legal and regulatory standards.

This guide provides an explanation of this use case, covering:

<li> How audit events are captured and formatted using FHIR</li>
<li> How to send AuditEvent resources to NHS Spine using a FHIR API</li>
<li> The key data elements included in an audit event </li>


</div>

{{index:root}}

