## {{page-title}}

In the previous section the ability to convey what the patient has and has not got access to was mentioned. Using the information from the API it is possible to present the information to the patient rather than have the application convey the levels of access.

In order to do this in a way such that the levels of access make sense to patient the application would need to find a way to explain what the different permission levels represent and what each level provides access to. Ideally this would be done with a focus on the outcome the patient could expect - for example, if the patient wanted to see their test results, they would need to have `Detailed` (coded record) access.

This is a challenging problem for consuming applications to solve and should ideally be done by learning about their patients, working out how best to express the ideas of permissions, access and how patients are able to best achieve their objectives.

Following on from the presentation of permission information to the patient is the ability to allow the patient to request changes to the permissions they have. See {{pagelink:Home/Build/How-to-request-a-change-to-a-patient-s-permissions}} for additional information.