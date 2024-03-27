## {{page-title}}

This is the priority given by the GP practice for the referral. This may differ from the priority given to the referral by the recipient.

The `priority` is a restricted valueset mapped to the eRS priority codes. The source GP clinical system may support priority values other than the eRS priority codes. If the priority in the source system is not one of the eRS priority codes and cannot be mapped to an eRS priority code, then a `priority` **MUST NOT** be included and the source system priority **MUST** be included as a key value pair in the `note` element.