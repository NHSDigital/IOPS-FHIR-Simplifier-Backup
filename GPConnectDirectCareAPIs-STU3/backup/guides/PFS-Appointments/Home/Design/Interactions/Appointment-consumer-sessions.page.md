---
topic: appointment-consumer-sessions
---

## {{page-title}}

The Appointment Management consumer application makes use of individual API calls described in 'API use cases' to perform business processes. 

## Consumer session - booking an appointment ##

The sequence diagram below illustrates which individual API calls are required by a consumer (that is, the patient using a consumer application) to book an appointment at a GP practice in the simplest case. It describes interactions of the consumer system with the provider FHIR endpoint at the practice.

Sequence diagram for booking an appointment - simplest case:

{{render:pfs_sequence_book_simple.png}}


| Step | Description |
|------|-------------|
| 1a   | **Consumer** makes an API call to {{pagelink:how-to-search-for-free-slots}} at the practice in the specified timeframe. |
| 1b   | **Provider** responds with details of what slots are available for booking. Should no applicable slots be returned, the consumer may make repeated calls to {{pagelink:how-to-search-for-free-slots}} with amended date ranges. |
|      |      |
| 2a   | **Consumer** calls {{pagelink:how-to-book-an-appointment}} indicating the slots selected in the UI together with the logical ID of the patient. |
| 2b   | **Provider** responds with details of the booked appointment as confirmation of success. |


## Consumer session - booking an appointment at a collection of federating practices ##

Where a consumer user interface provides a view of available bookings across a collection of federating practices, some steps are repeated for each practice, as shown below:

Sequence diagram for booking an appointment - no patient found: 

{{render:pfs_sequence_book_simple_federated.png}}


| Step | Description |
|------|-------------|
|      | *Repeat step 1 for each federated practice to gain a view of slot availability across the federation.* | 
| 1a   | **Consumer** makes an API call to {{pagelink:how-to-search-for-free-slots}} at the practice in the specified timeframe. |
| 1b   | **Provider** responds with details of what slots are available for booking. Should no applicable slots be returned, the consumer may make repeated calls to {{pagelink:how-to-search-for-free-slots}} with amended date ranges. |
|      |      |
| 2a   | **Consumer** calls {{pagelink:how-to-book-an-appointment}}  indicating the slots selected in the UI together with the logical ID of the patient. |
| 2b   | **Provider** responds with details of the booked appointment as confirmation of success. |


