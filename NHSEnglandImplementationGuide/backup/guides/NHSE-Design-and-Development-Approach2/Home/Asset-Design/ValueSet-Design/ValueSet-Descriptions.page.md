## {{page-title}}

A free text natural language description of the of the ValueSet from a consumer's perspective. The textual description specifies the span of meanings for concepts to be included within the ValueSet Expansion, and also may specify the intended use and limitations of the ValueSet. In the NHS England IG there is a preference to use the words &quot;define&quot; or &quot;describe&quot; and more rarely, &quot;identify&quot;.
<br/><br/>
The prefix SHOULD be as follows:

```xml
A set of codes that define [description].
```

<br><br>
For SNOMED CT and dm+d concepts, the following SHOULD be added after the prefix:

- For a ValueSet containing a set of SNOMED Reference Sets and/or hierarchies and/or individual concepts:

```xml
Selected from the following SNOMED CT UK coding system: \n 
- [long syntax1] [RefSet/hierarchy1 code] - [description of RefSet/hierarchy1] \n
- [long syntax2] [RefSet/hierarchy2 code] - [description of RefSet/hierarchy2] \n,  etc. 
```

- Where the ValueSet include dm+d concept classes:
```xml
Selected from the following dm+d (dictionary of medicines and devices) concept classes:\n
[concept1]-[description1] \n
[concept2]-[description2] \n, etc.
```

<br><br>
Where the ValueSet includes nullFlavor(s) in addition to other sets of codes, the suffix SHOULD be as the following:<br/>
```xml
Where no [MainCodeSystems] coded information is available, a specific code from the nullFlavor CodeSystem can be used instead to indicate this.
```

For complicated descriptions, particularly where a complex set of SNOMED references is used, and where inclusion of a carriage return / line feed can make the content more presentable in Simplifier, the sequence &#13; can be inserted to start a new line and &#13;&#13; can be inserted to leave a line break before the next line starts.

---

