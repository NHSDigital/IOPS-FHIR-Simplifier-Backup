## {{page-title}}
This contains any relevant information specifically to the profile. Within this page it may contain use cases or the minimum viable content. The title SHALL be added to the index page, but any information below is optional. 

~~~html
## Profile Specific Implementation Guidance: ##

[add any specific implementation or use case guidance]
~~~

If a profile is derived, it SHALL include a \{ \{pagelink}} to the parent profile as per the examples below:

~~~html
## Profile Specific Implementation Guidance: ##

This is a derived profile of { {pagelink:Profile-Observation,text:UKCore-Observation}} and this page only shows the differences between the two. Refer to the base Profile for more implementation guidance.
~~~

or

~~~html
## Profile Specific Implementation Guidance: ##

The UKCore-Observation-VitalSigns-BloodPressure profile further derives from { {pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}} and this page only shows the differences between the two. Refer to { {pagelink:Profile-Observation,text:UKCore-Observation}} and { {pagelink:Profile-Observation-VitalSigns,text:UKCore-Observation-VitalSigns}} for more implementation guidance.
~~~

---