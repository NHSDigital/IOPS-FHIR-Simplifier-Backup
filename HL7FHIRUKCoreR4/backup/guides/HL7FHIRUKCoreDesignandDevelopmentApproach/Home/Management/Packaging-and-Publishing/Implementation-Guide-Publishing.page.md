## Implementation Guide Release

### Prerequisites
Once the package has been created the IG can be published. Within the IG editor:

<ol>
<li>Click the hamburger. Click Settings
 <br><br>
 {{render:igsettings}}
 <br><br>
  Add the title UK Core Implemetation Guide STUx Sequence, where x is the STU number. Add a description
  <br><br>
 {{render:igsettingstitle}}
 <br><br>
  Change the scope to point to the newly created package and click save.
 <br><br></li>
<li>Select Edit Master Template.
<br><Br>
 {{render:igmastertemplate}}
 <br><Br>
  Comment out development notice information if it is no longer applicable, approximately lines 54 to 63, using `<!-- [block of code] -->`
  <br><Br>
 {{render:igmastertemplatecomment}}
<br><Br>
  Update the details of the bottom banner, namely the Released date (approximately line 91).
 <br><br></li>
<li>Amend the Contact Us page
<ul> 
<li>Change the version on the first paragraph</li>
<li>Change the version for each email subject line to read</li>
<li>Subject=UK Core Release #version </li>
</ul>
</li>
<li>Amend the new package on the Downloads page</li>
<li>Before publishing it is vital to check that:
<ul> 
<li>All pages and links are rendered correctly</li>
<li>The IG has been run through spell-checking software</li>
<li>The IG has been run though a link checking software </li>
</ul></li>
</ol>

---

### Publishing a Guide

<ol>
<li>Within the Guides portal select the burger bar next to the guide you want to publish and select versions.
<br><br>
{{render:igpublish}}
<br><br></li>
<li>Select the burger bar next to the version that you want publishing and select publish.
  <ul>
    <li>Enter the agreed version (this may align with the package version).</li>
    <li>Ensure that:
      <ul>
      <li>Status is set to Public</li>
      <li>Read-only is set to Read-only
      <li>Make default set to Yes </li>
      </ul>
    <br><br>
    {{render:igpublishversion}}
    <br><br>
    </li>
  </ul>
</li>
<li>Select Publish</li>
</ol>

---

### Overwriting and Republishing a Guide

If there are any errors spotted after publishing the guide it is possible to overwrite and republish using the same version number.

<ol>
<li>Within the Guides portal select the burger bar next to the guide you want to publish and select 'Make overwritable'.</li>
<li>From the current burger bar select publish.
 <br><br>
 {{render:igoverwitepublish}}
 <br><br>
 <ul>
  <li>Enter the same version number of the previous guide that you have just made overwritable. This may be different to the package version.</li>
  <li>Ensure that:
    <ul>
    <li>Status is set to Public</li>
    <li>Read-only is set to Read-only
    <li>Make default set to Yes </li>
    </ul>
  </li>
 </ul>
 </li>
<li>Select Publish.</li>
</ol>

<hr class="thickline">