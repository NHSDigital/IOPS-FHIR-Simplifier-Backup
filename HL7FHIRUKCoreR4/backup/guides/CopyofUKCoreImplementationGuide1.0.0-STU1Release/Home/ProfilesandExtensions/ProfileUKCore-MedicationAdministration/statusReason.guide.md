## `statusReason`

A coded reason for why an administration was not performed.

Should only be populated when the `status` is `stopped`.

---
<!--

Guidance states for when status = “stopped”

Should this also apply for “not-done” (prior to any impact on the subject)?

Example binding:
182895007  | Drug declined by patient - alternative therapy (situation)
      Drug declined by patient - cannot pay script (situation)
      Drug declined by patient - dislikes taste (situation)
      Drug declined by patient - inconvenient (situation)
      Drug declined by patient - patient beliefs (situation)
      Drug declined by patient - problem swallowing (situation)
      Drug declined by patient - reason unknown (situation)
      Drug declined by patient - side effects (situation)
242990004 | Drug not available for administration (event)

Does this value set may need to be extended?

Ian Rubin - lots of reasons why stopped - the above value set is not sufficient.

More thinking needed on this one.

-->