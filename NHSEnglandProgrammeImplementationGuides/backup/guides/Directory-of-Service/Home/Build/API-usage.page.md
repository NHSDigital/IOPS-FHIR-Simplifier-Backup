## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>



## Endpoints

- GET /HealthcareService
- GET /HealthcareService.location
- GET /HealthcareService.type

- GET /Slot
- GET /Schedule.actor:HealthcareService
- GET /Schedule:actor:PractitionerRole

GET /Slot?start=ge2024-06-01T13:00:00+00:00&start=le2024-06-01T13:30:00+00:00</br>
_include</br>
Slot:schedule</br>
&Schedule:actor:HealthcareService="20091234"</br>
&Schedule:actor:PractitionerRole="Doctor"

Refer to - {{pagelink:Home/Design/Interactions.page.md}}. 