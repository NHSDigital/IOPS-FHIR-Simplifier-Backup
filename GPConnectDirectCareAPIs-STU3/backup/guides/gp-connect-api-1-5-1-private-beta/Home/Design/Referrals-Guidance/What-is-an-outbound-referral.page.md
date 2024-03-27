## {{page-title}}
This GP Connect profile represents a list of outbound referral events as recorded in the GP clinical system’s referral feature or categorised area.
The referral record represents the event of a referral being made or an intention to refer the patient (if the referral record has been recorded but the actual referral has yet to be sent). 
It does not reflect the acceptance of the referral by the recipient or any onward progress of the referral.

A referral is typically defined as a request for transfer of care or request to provide assessment, treatment or clinical advice on the care of a patient. 
This GP Connect profile is intended to align with this definition, but consumers should be aware that records may be included which are outside of the scope of this definition - see <a href="#classification-design-decision">Classification design decision</a>.

A referral may be considered as a detailed document containing relevant medical history, presenting needs, problem management to date, current medications, allergies and so on. 
As this profile is a record of the event of the referral, it does not itself contain such clinical background for the patient being referred. 
This profile may reference some clinical information, for example via a linked problem or consultation, but consumers should be aware that it may be necessary to access other parts of the clinical record to obtain the full clinical context.

Inbound referrals are to be returned as {{pagelink:Home/Design/Uncategorised-data-guidance}}.