## {{page-title}}

GP Connect queries/requests may be received while the patient’s record is being updated.

Record locking inside a provider system **MUST NOT** impact the ability of the system to fulfil read/query requests of the patient’s record.

However, it is understood that there are differing approaches to record locking within the GP principal systems which have an effect when any local/pending changes are actually committed back to the patient’s record.

When a consumer system accesses a patient’s record, the provider systems **MUST** only return data that has been successfully committed back to the patient’s record and thus has become available to all users (including users of the provider APIs).

