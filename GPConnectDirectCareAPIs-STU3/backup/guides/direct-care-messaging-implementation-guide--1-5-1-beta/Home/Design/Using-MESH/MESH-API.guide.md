## {{page-title}}

The MESH API is a simple REST HTTP API which enables message senders to send messages through MESH. Please refer to the MESH API specification for details.

When using the MESH endpoint lookup service, the `Mex-To` HTTP header is populated according to the following syntactic conventions.

`<GPPROVIDER>[delimiter]<Nhs No>[delimiter]<d.o.b>[delimiter]<Surname>`

The underscore `_` character is used as the delimiter.

Date of birth is specified in `YYYYMMDD` format.

For example, when sending a message about a patient:

> Mr Brian Smith, born 14 February 2001, with NHS Number 12345678

The `Mex_To` field will have the following value:

`GPPROVIDER_12345678_20010214_Smith`

---