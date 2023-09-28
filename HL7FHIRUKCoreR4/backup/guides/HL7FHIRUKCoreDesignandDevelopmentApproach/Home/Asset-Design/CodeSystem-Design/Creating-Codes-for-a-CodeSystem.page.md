## {{page-title}}

Where they don't already exist, the UK Core approach to creating codes for concepts in a new CodeSystem is by placing a hyphen between each word of the display value (if they contain more than one word) and using solely lower case alphabetic characters. For example:

``` xml
<concept>
        <code value="prescribed-at-gp-practice" />
        <display value="Prescribed at GP practice" />
    </concept>
```

An exception to this is where the CodeSystem is a copy of a Data Dictionary set of concepts from any of the UK nations, where the approach is to faithfully use both the code and its description within the CodeSystem as defined within the Data Dictionary source at the time of creation of the CodeSystem.
Note that for some CodeSystems already in existence in the UK core, including content previously created for other projects, alternative code construction forms have also been used.

---

