## {{page-title}} - ValueSets containing NHS England CodeSystems

### Content Logical Definition - Single code system ###

```xml
<compose>
    <include>
        <system value="https://fhir.nhs.uk/CodeSystem/England-[ConcatenatedBusinessName(s)]" />
    </include>
</compose>
```

### Content Logical Definition – Selected included codes from a single code system ###

```xml
<compose>
    <include>
        <system value="https://fhir.nhs.uk/CodeSystem/England-[ConcatenatedBusinessName(s)]" />
        <concept>
            <code value="[conceptCode1]" />
            <display value="[conceptDisplay1]" />
        </concept>
        <concept>
            <code value="[conceptCode2]" />
            <display value="[conceptDisplay2]" />
        </concept>
    </include>
</compose>
```

### Content Logical Definition – Selected excluded codes from a single code system ###

``` xml
<compose>
    <include>
        <system value="https://fhir.nhs.uk/CodeSystem/England-[ConcatenatedBusinessName(s)]" />
    </include>
    <exclude>
        <system value="https://fhir.nhs.uk/CodeSystem/England-[ConcatenatedBusinessName(s)]" />
        <concept>
            <code value="[conceptCode1]" />
            <display value="[conceptDisplay2]" />
        </concept>
        <concept>
            <code value="[conceptCode2]" />
            <display value="[conceptDisplay2]" />
        </concept>
    </exclude>
</compose>
```

<span id="snomed_cld"></span>
### Content Logical Definition – ValueSets containing SNOMED concepts ###

The NHS England approach is that all SNOMED is encapsulated within the Content Logical Definition using SNOMED Expression Constraint Language (ECL) in a single statement in the value element, together with a property element value of "constraint" and an op element value of "=".

More information about <a href="https://confluence.ihtsdotools.org/display/DOCECL" Target="_blank">ECL</a> and <a href="https://terminology.hl7.org/SNOMEDCT.html">Using SNOMED CT with HL7 Standards</a> is available online.

The ECL informative long syntax SHALL be used to identify a hierarchy or reference set within the NHS England IG to both provide greater clarity to a potentially wide audience and to simplify the process of creating, validating and using the ECL statement for a range of potential users as it avoids any need to encode and decode symbols otherwise used in the brief syntax.

Concept display values SHALL NOT be included in the ECL statement to avoid potential duplication with the ValueSet description and to avoid any need to encode separator characters. The ValueSet description field is used to provide hierarchy / reference set display name information, although display values for lists of individual codes will only be available via a ValueSet expansion, again to avoid duplication.


```xml
<compose>
    <include>
        <system value="http://snomed.info/sct" />
        <filter>
            <property value="constraint" />
            <op value="=" />
            <value value="[long syntax1] [SNOMED CT Code1] OR [long syntax2] [SNOMED CT Code2] OR , etc." />
        </filter>
    </include>
</compose>
```

### Content Logical Definition – ValueSets containing dm+d concepts ###

```xml
<compose>
    <include>
        <system value="https://dmd.nhs.uk" />
        <filter>
            <property value="parent" />
            <op value="=" />
            <value value="[ValueSet1]" />
        </filter>
    </include>
    <include>
        <system value="https://dmd.nhs.uk" />
        <filter>
            <property value="parent" />
            <op value="=" />
            <value value="[ValueSet1]" />
        </filter>
    </include>
</compose>
```

---
