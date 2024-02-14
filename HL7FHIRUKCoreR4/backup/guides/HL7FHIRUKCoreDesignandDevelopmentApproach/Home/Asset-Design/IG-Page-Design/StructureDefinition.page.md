## {{page-title}}

The structure definition contains the profile’s description and profile purpose, rendered from the xml file using Firely Query Language (FQL). This contains a short description of the profiles purpose and the profile itself within a table. The profile table reference SHALL be rendered as below, ensuring that each view has the correct profile link. 

The tabs and rendered views SHALL be enclosed within a <code>\<nocheck></code> tag to allow for skipping of the spell checker due to the many spelling mistakes within the base HL7 render.

All examples relating to the profile, including those for extensions in the profile, SHALL be included within the Examples view. A profile SHALL have at least one example. 

Profile pages built for STU3 Ballot and beyond, SHALL have a `system` within the YAML header, and can replace the snapshot / differential / hybrid tabs, with a single TreeView tab, and utilize the new Simplifier buttons, as these render the page faster. In addition, these should include the new Usage tab. These can all be done via a template.

~~~~html
# StructureDefinition { {variable:issue}}

<nocheck>
{ {page:Home/ProfilesandExtensions/ProfileTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
<b>[profile]</b> - An example to illustrate the [reason for example].
<br>{ {pagelink:Example-UKCore-[profile]}}
</div>
</nocheck>
~~~~

---