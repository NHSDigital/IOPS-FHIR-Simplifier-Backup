## Timing Elements: `frequency` and `period`

A large proportion of cases, especially those where the medication are described using a VMP or AMP concept, can have a dosage instruction defined with a combination of `frequency` and `period` elements within the [Timing structure.](http://hl7.org/fhir/STU3/datatypes.html#Timing)

Simple dosage timing instructions can be described using `frequency` and `period`.

The combination of frequency and period allows for the two commonly used expressions of:

- x times a period
- every x period

The unit of the period must be one of the UCUM units:

<table table-responsive>
    <thead>
        <tr>
            <th>UCUM Unit</th>
            <th>Definition</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><code>s</code></td>
            <td>second</td>
        </tr>
        <tr>
            <td><code>min</code></td>
            <td>minute</td>
        </tr>
        <tr>
            <td><code>h</code></td>
            <td>hour</td>
        </tr>
        <tr>
            <td><code>d</code></td>
            <td>day</td>
        </tr>
        <tr>
            <td><code>wk</code></td>
            <td>week</td>
        </tr>
        <tr>
            <td><code>mo</code></td>
            <td>month</td>
        </tr>
        <tr>
            <td><code>a</code></td>
            <td>year</td>
        </tr>
    </tbody>
</table>

A **frequencyMax** and/or **periodMax** can also be used to define ranges. The FHIR specification states if there's a **periodMax**, there must be a **period**.

**Every 8 hours**

```xml
<timing>
    <repeat>
        <frequency value="1"/>
        <period value="8"/>
        <periodUnit value="h"/>
    </repeat>
</timing>
```

**4 times a day**

```xml
<timing>
    <repeat>
        <frequency value="4"/>
        <period value="1"/>
        <periodUnit value="d"/>
    </repeat>
</timing>
```

**2 to 4 times a day**

```xml
<timing>
    <repeat>
        <frequency value="2"/>
        <frequencyMax value="4"/>
        <period value="1"/>
        <periodUnit value="d"/>
    </repeat>
</timing>
```

**every 3 to 4 weeks**

```xml
<timing>
    <repeat>
        <frequency value="1"/>
        <period value="3"/>
        <periodMax value="4"/>
        <periodUnit value="wk"/>
    </repeat>
</timing>
```

**3 to 4 times every 1 to 2 weeks**

```xml
<timing>
    <repeat>
        <frequency value="3"/>
        <frequencyMax value="4"/>
        <period value="1"/>
        <periodMax value="2"/>
        <periodUnit value="wk"/>
    </repeat>
</timing>
```

**daily**

```xml
<timing>
    <repeat>
        <frequency value="1"/>
        <period value="1"/>
        <periodUnit value="d"/>
    </repeat>
</timing>
```

**twice a week**

```xml
<timing>
    <repeat>
        <frequency value="2"/>
        <period value="1"/>
        <periodUnit value="wk"/>
    </repeat>
</timing>
```

### Examples of potentially confusing timing instructions

When converting the information into a FHIR message to a human readable version the frequency could be misconstrued.

For example:

`take twice a week on a Monday and Thursday`

Is the patient being instructed to take the medication twice **per day** on a Monday and Thursday (4 individual doses), or twice **per week** on a Monday and Thursday (2 individual doses)?

<div class="nhsd-a-box nhsd-a-box--bg-red nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong class="emphasis-box__heading">Bad ambiguious example:</strong>
    <br />
    on Monday and Thursday - take twice
</div>

```xml
<timing>
    <repeat>
        <count value="2" />
        <dayOfWeek value="mon" />
        <dayOfWeek value="thu" />
    </repeat>
</timing>
```
Using the dose-to-text guidance within this documentation the above would be displayed as:

`on Monday and Thursday - take twice`

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong class="emphasis-box__heading">Better specific example:</strong>
    <br />
    twice a week - on Monday and Thursday
</div>

```xml
<timing>
    <repeat>
        <frequency value="2"/>
        <period value="1" />
        <periodUnit value="wk"/>
        <dayOfWeek value="mon" />
        <dayOfWeek value="thu" />
    </repeat>
</timing>
```
Using the dose-to-text guidance within this documentation the above would be displayed as:

`twice a week - on Monday and Thursday`

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <strong class="emphasis-box__heading">Alternative better specific example:</strong>
    <br />
    on Monday and Thursday
</div>

```xml
<timing>
    <repeat>
        <dayOfWeek value="mon" />
        <dayOfWeek value="thu" />
    </repeat>
</timing>
```
Using the dose-to-text guidance within this documentation the above would be displayed as:

`on Monday and Thursday`

<br />

**Real-World Example**

This prescription is used for immunocompromised patients to provide prophylaxis against a particular strain of pneumonia.

<a href="https://simplifier.net/guide/DoseSyntaxImplementationforFHIRSTU3/StandardDoseSyntax#Co-trimoxazole80mg400mgtabletsActavisUKLtdone"><b>Co-trimoxazole 80mg/400mg tablets (Actavis UK Ltd)</b> - 1 tablet - twice a day - on Monday, Wednesday and Friday.</a> 



---