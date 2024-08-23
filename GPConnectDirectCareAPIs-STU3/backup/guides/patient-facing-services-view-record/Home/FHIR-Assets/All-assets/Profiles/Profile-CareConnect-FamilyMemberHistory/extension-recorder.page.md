## {{page-title}}

Usage
Mandatory

Guidance
The person who entered the record on the system. The table below outlines requester and recorder combinations for clarity.

Scenario	Requester	Recorder
Prescibing clinician Fred is requesting new medication	Fred	Fred
Prescibing clinician Fred is re-ordering previous medication he previously prescribed	Fred	Fred
Prescibing clinician Jane is re-ordering previous medication, without any clinical changes, that Fred previously prescribed	Fred	Jane
Prescibing clinician Jane is re-ordering previous medication that Fred previously prescribed, with clinical changes	Jane	Jane
Nurse Rodger is ordering medication prescribed by Fred	Fred	Rodger
Pharmacy technical Sally is re-ordering medication prescribed by Fred	Fred	Sally
Example

```xml
<recorder>
    <identifier>
        <system value="https://fhir.hl7.org.uk/Id/gmc-number" />
        <value value="0054272" />
    </identifier>
 </recorder>
 ```

---