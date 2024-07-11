## {{page-title}}


### Introduction

### Actors and Transactions, and Content Module

### Actor Options

### Actor Required Grouping

### Overview

#### Basic Tasking

{{render:tasking-overview}}

Tasking is also conversation, rather then messaging based (see https://www.enterpriseintegrationpatterns.com/patterns/conversation/index.html). This allows the interactions to more closely follow business requirements and not be focused on transferring data.

<plantuml>
@startuml
  
hide footbox
  
title "Conversational Request"
  
participant Placer
participant Filler
  
  
Placer->Filler: Can you? (validate my prescription)
opt accepted
Filler->Placer: Yes, I accept
Filler->Placer: It's in progress
Filler->Filler: Action request
Filler->Placer: It's completed and it is fine
else rejected
Filler->Placer: Sorry, I need to reject this request
end
  
  
@enduml
</plantuml>

The interactions have a state machine which indicates the progress of the request.

#### Task State Machine

<plantuml>
@startuml
 
 
state Taskstatus as "Tasks.status" {
}
 
 
 
[*] --> Taskstatus.draft
Taskstatus.draft --> Taskstatus.requested
Taskstatus.draft --> Taskstatus.ready
Taskstatus.requested --> Taskstatus.accepted
Taskstatus.requested --> Taskstatus.received
Taskstatus.requested --> Taskstatus.rejected
Taskstatus.received --> Taskstatus.accepted
Taskstatus.received --> Taskstatus.rejected
Taskstatus.ready --> Taskstatus.inprogress
Taskstatus.accepted --> Taskstatus.inprogress
Taskstatus.accepted --> Taskstatus.cancelled
Taskstatus.ready --> Taskstatus.cancelled
Taskstatus.requested --> Taskstatus.cancelled
Taskstatus.received --> Taskstatus.cancelled
Taskstatus.rejected --> Taskstatus.cancelled
Taskstatus.inprogress --> Taskstatus.completed
Taskstatus.inprogress --> Taskstatus.failed

Taskstatus.failed --> [*]
Taskstatus.completed --> [*]
Taskstatus.rejected --> [*]
Taskstatus.cancelled --> [*]
 
@enduml
</plantuml>

#### Patient Encounter Notifications

