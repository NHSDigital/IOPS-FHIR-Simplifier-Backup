## <code>{{page-title}}</code>

The root of the sections that make up the composition. Section may be nested as required.

The following child elements should be used:

-  `Composition.section.title` The label for this particular section. This will be part of the rendered content for the document, and is often used to build a table of contents.
-  `	Composition.section.code` A code identifying the kind of content contained within the section. This must be consistent with the section title. This should use a code from {{pagelink:ValueSetUKCoreCompositionSectionCode-110}}.
-  	`Composition.section.text` 	A human-readable narrative that contains the attested content of the section, used to represent the content of the resource to a human. The narrative need not encode all the structured data, but is required to contain sufficient detail to make it "clinically safe" for a human to just read the narrative.
- `Composition.section.entry` A reference to the actual resource from which the narrative in the section is derived. If there are no entries in the list, an emptyReason SHOULD be provided.
- `Composition.section.emptyReason` If the section is empty, why the list is empty. An empty section typically has some text explaining the empty reason.

**Invariants that affect this element:**
**cmp-2**	Rule: A section can only have an emptyReason if it is empty	emptyReason.empty() or entry.empty()

---

