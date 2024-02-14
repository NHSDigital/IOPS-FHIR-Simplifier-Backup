## {{page-title}}

Extensions SHALL have a page within the ‘All Extensions’ folder with the naming convention of ‘Extension UKCore-<i>[extensionName]</i>’, and you must ensure the pages within the folder are in alphabetical order.  

Each extension SHALL have an example.  

The page layout SHALL be as the following: 

~~~~html
---
subject: [Extension URL]
issue: [Extension ID]
---
## StructureDefinition { {variable:issue}}

<table id="addToTranspose">
<tr><td>Context of Use</td>
<td>{ {pagelink:Profile-[Profile],text:[Profile]}}</td>
</tr>
</table>

{ {page:Home/ProfilesandExtensions/ExtensionTemplate.page.md}}

<div id="Examples" class="tabcontent">
  <h3>Examples</h3>
  <b>[Example]</b> - An example to illustrate using the extension.<br>
{ {pagelink:Example-UKCore-[Profile]-Extension-[ExtensionName]}}
<br><br>
</div>

<h3 id="guidance-{ {variable:issue}}">Extension Specific Guidance</h3>
[A link to the ValueSet if the Extension has a binding, or a link to the Resource / Profile if the Extension has references]

---
~~~~

---