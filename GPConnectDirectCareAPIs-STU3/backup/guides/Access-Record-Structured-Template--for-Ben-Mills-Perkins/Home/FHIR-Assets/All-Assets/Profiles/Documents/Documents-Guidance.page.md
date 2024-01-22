# {{page-title}}

## Introduction

A clinical document (CD) is a written, printed or electronic record that provides evidence of medical care. Clinical documents must be accurate, timely and reflect specific services provided to a patient. A clinical document could be any document that the GP practice adds to a clinical record of the patient.

## Returning document metadata in Access Record Structured

When querying for consultations and problems, [DocumentReference](access_documents_development_documentreference.html) resources containing document metadata will be returned for any linked documents. The document location will be returned alongside the metadata so that consumers can retrieve the [Binary](access_documents_development_binary.html) resource for the document. In order to do this, consumers will need to have been assured against the [Access Document](access_documents.html) capability.

<div class="alert alert-warning nhsd-t-body" role="alert">
<i class="fa fa-exclamation-triangle"></i> <b>Important:</b> - Fix the 3 links above<br/> </div>