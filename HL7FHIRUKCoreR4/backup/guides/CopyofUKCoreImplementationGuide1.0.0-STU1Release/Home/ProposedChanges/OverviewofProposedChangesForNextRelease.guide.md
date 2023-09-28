---
topic: Home-ProposedChanges-3c6f1d00-63d2-418b-ad6c-b8618665fe54
---

## {{page-title}}
This section documents proposed changes to be applied to the UK Core for the next release. These are highlighted to allow reviewers to comment on the proposed changes. Solutions for the issues which lead to these proposed changes may have been discussed on the C&TA sprint calls but can still be challenged by any reviewer.

<table id="assets">
<tr>
<th width="5%">Number</th>
<th width="50%">Issue</th>
<th width="45%">Proposal</th>
</tr>

<tr>
<td>{{pagelink:Issue1-110}}</td>
<td>Sprint 4 extensions are not currently explicitly bound to the profiles they are used in.</td>
<td>All Sprint 4 extensions to be explicitly bound to the profiles they are used in, to align with the approach taken in sprints 1 to 3.</td>
</tr>

<tr>
<td>{{pagelink:Issue2-110}}</td>
<td>Some profile references within Sprint 4 profiles do not currently reference UK Core specific profiles where they exist in the UK Core, whereas others do.</td>
<td>All profile references within all profiles covered by Sprint 4 to be changed to UK Core specific profiles where they exist within the UK Core, to align with the approach taken in sprints 1 to 3.</td>
</tr>

<tr>
<td>{{pagelink:Issue3-110}}</td>
<td>Some Sprint 4 ValueSets contain only a single CodeSystem based on England specific Data Dictionary concepts.</td>
<td>Additional CodeSystems supporting concepts from other UK countries will be incorporated into such ValueSets.</td>
</tr>

<tr>
<td>{{pagelink:Issue4-110}}</td>
<td>The use of slicing for elements where a UK Core ValueSet is specified with just SNOMED content is still present in some Sprint 4 profiles. Such slicing was removed from profiles covered by Sprints 1 to 3, as the slicing was only used to structurally allow for the inclusion of the Extension UKCoreCodingSCTDescId and a decision was made to use guidance to describe when and how to use that extension instead.</td>
<td>Where a SNOMED slice has been specified, the slice will be removed and any UK Core binding that had been applied to that slice will be moved to the element which has been sliced.</td>
</tr>

<tr>
<td>{{pagelink:Issue5-110}}</td>
<td>The use of the "Extensible" binding strength on ValueSets specifying only the use of SNOMED potentially places a burden on many implementations to provide a mapping to a CodeSystem (SNOMED) that either is not used natively or in which legacy data was not recorded, if the FHIR standard requirements relating to the use of a ValueSet with an "Extensible" binding strength are to be adhered to.</td>
<td>The use of the "Extensible" binding strength on ValueSets specifying only the use of SNOMED needs to be reviewed. This also needs to be applied to ValueSets from Sprints 1 to 3. Where the use of "Extensible" is not deemed to be appropriate, the use of "Preferred" will be proposed.</td>
</tr>

<tr>
<td>{{pagelink:Issue6-110}}</td>
<td>There are two Sprint 4 extensions that carry the same content, which is a single element bound to the same UKCoreCareSettingType ValueSet: UK Core Care Setting Type and UK Core Clinical Setting.</td>
<td>Only one such extension is needed.</td>
</tr>

<tr>
<td>{{pagelink:Issue7-110}}</td>
<td>The UKCoreListEmptyReasonCode ValueSet only contains a single concept (No Content Recorded). The FHIR standard ValueSet which it has replaced contains a number of concepts that would also be useful in a UK context (the concepts are: Nil Known | Not Asked | Information Withheld | Unavailable | Not Started | Closed).</td>
<td>The UKCoreListEmptyReasonCode ValueSet will be updated to also include the FHIR Standard List Empty Reasons CodeSystem: <a href="https://hl7.org/fhir/codesystem-list-empty-reason.html">https://hl7.org/fhir/codesystem-list-empty-reason.html</a>.</td>
</tr>

<tr>
<td>{{pagelink:Issue8-110}}</td>
<td>The UK Core currently does not support a data item present in the PRSB Core Information Standard: Legal Status on Admission.</td>
<td>During Sprint 4 Clinical and Technical Assurance calls, it was agreed that the UK Core should also support this data item. It was also agreed that the UK Core should support a Legal Status on Discharge, using the same set of concepts as for Legal Status on Admission.</td>
</tr>

<tr>
<td>{{pagelink:Issue9-110}}</td>
<td>No use case for the use of the Encounter Transport extension has been identified.</td>
<td>The Encounter Transport extension will be removed from the UK Core.</td>
</tr>

<tr>
<td>{{pagelink:Issue10-110}}</td>
<td>The UK Core currently does not align with the ValueSet specified in the PRSB Core Information Standard for Encounter Service (Encounter.serviceType profile element).</td>
<td>The binding for the Encounter.serviceType profile element, which is currently to a FHIR standard example ValueSet, will be changed to the UKCoreCareSettingType ValueSet</td>
</tr>

<tr>
<td>{{pagelink:Issue11-110}}</td>
<td>The UK Core currently does not align with the ValueSet specified in the PRSB Core Information Standard for Encounter Location Type (Encounter.location.physicalType profile element).</td>
<td>The binding for the Encounter.location.physicalType element, which is currently to a FHIR standard example ValueSet, will be changed to a new UK Core ValueSet in order to align with the PRSB Core Information Standard.</td>
</tr>

<tr>
<td>{{pagelink:Issue12-110}}</td>
<td>Three of the Sprint 4 UK Core profiles have elements that are currently bound to the UKCoreConditionCode ValueSet. However, this ValueSet is not composed of the same content as the three equivalent PRSB Core Information Standard data items. The profiles/element concerned are: Condition.code, Procedure.complication and Extension-UKCoreAnaestheticIssues.value[x].</td>
<td>The UK Core ValueSet bindings for these elements are changed where necessary to match the mappings provided in the PRSB Core Information Standard, which are currently being reviewed.</td>
</tr>

<tr>
<td>{{pagelink:Issue13-110}}</td>
<td>The Condition.verificationStatus element was constrained out of the Care Connect Condition profile.</td>
<td>During Sprint 4 Clinical and Technical Assurance calls, it was agreed that the UK Core should support the Condition.verificationStatus element.</td>
</tr>

<tr>
<td>{{pagelink:Issue14-110}}</td>
<td>No UK Core specific ValueSet is present in the UK Core to support three of the concepts that were available in the Care Connect ValueSet for the Condition.category element.</td>
<td>During Sprint 4 Clinical and Technical Assurance calls, it was agreed that the UK Core should also support those three concepts that were previously available in the Care Connect version (Presenting Complaint | Co-morbidity | Issue).</td>
</tr>

<tr>
<td>{{pagelink:Issue15-110}}</td>
<td>The FHIR standard ValueSet (ConditionStageType) bound to the stage.type element of the Condition profile needs to be reviewed for appropriateness in the UK.</td>
<td>Review comments on the appropriateness of this ValueSet from a UK perspective are welcome.</td>
</tr>

<tr>
<td>{{pagelink:Issue16-110}}</td>
<td>Guidance needs to be provided to implementers that the Procedure.status element is a modifier and that the presence of a procedure identified in the Procedure.code element also requires the implementer to look at the Procedure.status and Procedure.statusReason elements for the full context.</td>
<td>Guidance will be provided to inform implementers that the FHIR standard must be followed and that these items must be supported. Guidance will be issued to state that implementers must not just look at the Procedure.code element in isolation but also look at the Procedure.status and Procedure.statusReason elements as they may modify the context.</td>
</tr>

<tr>
<td>{{pagelink:Issue17-110}}</td>
<td>The relationship between the EpisodeOfCare and Encounter profiles may not be clear to implementers.</td>
<td>High level guidance on the use of the EpisodeOfCare profile and its relationship with the Encounter profile will be provided.</td>
</tr>

<tr>
<td>{{pagelink:Issue18-110}}</td>
<td>The UKCoreCompositionSectionCode ValueSet incorporates a SNOMED Clinical record headings simple reference set which now contains zero concepts.</td>
<td>The SNOMED reference set will be removed from the UKCoreCompositionSectionCode ValueSet Content Logical Definition, as the UKCoreRecordStandardHeadings which is also referenced in the Content Logical Definition covers all of the concepts that were in that reference set.</td>
</tr>

<tr>
<td>{{pagelink:Issue19-110}} </td>
<td>There is deemed to be a need to extend the MessageHeader to allow the ability to carry specific instructions for receivers of the message. For example please send an acknowledgement to confirm reciept of this message</td>
<td>Add generic extension to MessageHeader profile</td>
</tr>

<tr>
<td>{{pagelink:Issue20-110}} </td>
<td>There is deemed to be a need to define a common set of error codes for use across the UK</td>
<td>Create a CodeSystem for a common set of error codes if this is agreed as useful by the reviewers.</td>
</tr>
</table>