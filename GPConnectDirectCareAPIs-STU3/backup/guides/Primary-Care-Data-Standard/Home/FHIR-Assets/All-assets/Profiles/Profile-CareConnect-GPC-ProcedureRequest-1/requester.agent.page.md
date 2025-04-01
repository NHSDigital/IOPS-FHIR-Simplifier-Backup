## {{page-title}}

<h5><ins>Usage</ins></h5>

#### For investigations

<span class="mro-circle optional" title="Optional"></span> Optional

#### For diary entries

<span class="mro-circle required" title="Required"></span> Required

<h5><ins>Guidance</ins></h5>

#### For investigations

A use-case for the `requester.agent` element has not been defined.

#### For diary entries

This **MUST** be the practitioner who entered the diary entry in the original source system, if it was entered by a user. If the diary entry was system generated and it is not possible to meaningfully associate the diary entry to a system user then this **MUST** be a `Device` representing the providing system or an `Organization` representing the GP practice responsible for creating the record.

<h5><ins>Example</ins></h5>

```xml
<requester>
    <agent>
        <reference value="Practitioner/6c41ebfd-57c3-4162-9d7b-208c171a2fd7" />
    </agent>
</requester>
```
---