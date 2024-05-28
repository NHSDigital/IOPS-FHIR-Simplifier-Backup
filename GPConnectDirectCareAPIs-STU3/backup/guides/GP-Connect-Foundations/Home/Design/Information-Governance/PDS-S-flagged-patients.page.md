## {{page-title}}
Consumer systems **SHALL NOT** send GP Connect requests for S-flagged patients.

In cases where a request for an S-flagged patient is sent, provider systems **SHALL** return a ‘Patient Not Found’ error.