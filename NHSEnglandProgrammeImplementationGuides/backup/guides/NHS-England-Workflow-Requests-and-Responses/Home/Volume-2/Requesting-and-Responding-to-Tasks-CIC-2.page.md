## {{page-title}}


### Send Request

 <div markdown="span" class="alert alert-warning" role="alert"> POST /Task</div>

<plantuml>
@startuml
 
hide footbox
 
title Send Task [PCC-ENG-2]
 
 
actor "Request" as source
actor "Filler" as recipient
 
source -> recipient: Send Task [POST /Task]
recipient --> source: Acknowledgement
@enduml
</plantuml>



### Respond to a Request

 <div markdown="span" class="alert alert-warning" role="alert"> PUT /Task/{id}</div>

 or 

  <div markdown="span" class="alert alert-warning" role="alert"> PUT /Task?identifier={identifier}</div>

<plantuml>
@startuml
 
hide footbox
 
title Respond to Task [PCC-ENG-2]
 
 
actor "Request" as source
actor "Filler" as recipient
 
recipient -> source : Respond to Task [PUT /Task/{id}]
source --> recipient: Acknowledgement
@enduml
</plantuml>

