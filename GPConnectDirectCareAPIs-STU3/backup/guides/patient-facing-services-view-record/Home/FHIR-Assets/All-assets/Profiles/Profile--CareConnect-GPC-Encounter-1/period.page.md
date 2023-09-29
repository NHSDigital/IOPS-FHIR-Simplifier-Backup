## {{page-title}}

<h5><ins>Usage</ins></h5>

<span class="mro-circle required" title="Required"></span> Required


<h5><ins>Guidance</ins></h5>

The `period` element is a required element which means it **MUST** be populated with values when they are known to the provider system.

- The `period.start` represents the date and time when the consultation started.
- The `period.end` reperesents the date when populated and the duration is known.

The audit trail date time of the consultation is carried by the associated consultation list via `List.date`.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    The period attribute may be omitted where the effective / clinical date for the consultation on the source system is not recorded (for example, an unknown date and time).
</div>

<h5><ins>Example</ins></h5>

```xml
<period>
    <start value="2022-10-28T13:38:00+00:00" />
    <end value="2022-10-28T13:53:00+00:00" />
</period>
```

---