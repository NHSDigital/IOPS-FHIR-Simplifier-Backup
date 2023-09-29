## {{page-title}}

TODO This needs to read as a patient journey - So the process before Robert is in the ward in summary

HL7 v2 ADT concentrates on health administration event messaging and it largely ignores clinical event messaging. Here we mean important health events which other practitioners (and patients) should be made aware of. For example: 

 <div markdown="span" class="alert alert-warning" role="information">
<p>Robert had an abnormal SPO2 measurement (91%) on 15 Jun 2023 at 1322</p>
</div>

This event triggered Roberts pathway we have been discussing. It could have also occured in the ambulance, emergency department or the observation ward. It's possible this event would have triggered action by a practitioner or healh system.

Technically this would be solved via an [event messaging system](https://en.wikipedia.org/wiki/Event-driven_messaging) and/or [publish/subscribe pattern](https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern)

Here we are making a clear seperation between what data is recorded and what information is shared (notified). The previous section described a method for health administration notifications which was implemented using HL7 v2 ADT events. In our use case, the abnormal SPO2 measurement could have also been sent as an event.

{{render:diagrams-ModernWorkflowBPMN}}

This diagram uses [Business Process Model and Notation](https://www.bpmn.org/) to describe the workflow. BPMN diagrams often show a sequence of interconnected processes. In this diagram we have chosen to represent a high-level process which takes in

- **input** which is information required to perform the task. In our example the input is the abnormal SPO2 observation.
- **output** which is the information output from the task which is used to send key information to the next task. In our example, the abnormal observation triggered a ambulance dispatch request (via verbal communication).

These processes are commonly found in patient journey or pathway documentation. E.g. the process [Medicines reconciliation (NICE)](https://www.nice.org.uk/guidance/ng5/chapter/1-Recommendations#medicines-reconciliation) is found in several pathways.

Each process is normally an Encounter, this Encounter is documented in local records. Some of this encounter documentation is also **output**. 
Each process can use local record and shared records for additional **input**. 
Input and output often correlate with verbal communication used between practitioners delivering care, it is often a summary. E.g. 

<div markdown="span" class="alert alert-warning" role="information">
<p>Robert has been having breathing difficulties with an abnormal SPO2 measurement (91%)</p>
</div>

and not the detailed health records. 


