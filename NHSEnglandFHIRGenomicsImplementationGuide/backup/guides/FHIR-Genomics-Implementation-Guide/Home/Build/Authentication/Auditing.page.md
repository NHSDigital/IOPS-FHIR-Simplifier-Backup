## {{page-title}}

Audits will align to NHS England internal standards for national services.
- Logs will contain all interactions that occur on service.
- Logs will be designed and implemented to prevent editing or deleting of data by users.
- Logs will contain detail on processes within the service to support investigation into errors and issues.
- Logs will in the long run be connected to the NHS England Splunk logging process, but for the alpha will only be internal to the service as other services have proved the integration of cloud services with NHS England Splunk logging..
- The service will aim to minimise the storage of duplicate data, to reduce costs for running the service.
- Logging will be separated into PID data which needs to be retained under the retention policy and system logs which can be archived or removed sooner than the PID logs.

The mechanism for auditing test orders and responses is subject to the architecture chosen for the Genomic Medicine Service. It is expected that all messages submitted to the system, as well as access to records on the system, will be logged via {{pagelink:Profile-Genomics-AuditEvent}} resources to ensure all accesses and updates are auditable.

Updates to controlled documents, such as ServiceRequests and DiagnosticReports will further be accompanied by {{pagelink:Profile-Genomics-Provenance}} resources, submitted by clients, to capture who made a change and why.