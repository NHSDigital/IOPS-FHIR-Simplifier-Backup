## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fas fa-exclamation-triangle"></i><b> Important:</b> This page is under development by NHS England</div>


### Query for an FGM indicator

<br>

**HTTP request and headers**
<!--<div style="width: 300px; border: 1px solid darkgrey; padding: 10px; width: 100%">-->
<strong><font color="#00008B">GET</font></strong> /Flag?<br>&nbsp;&nbsp;&nbsp;patient:identifier=https://fhir.nhs.uk/Id/nhs-number|&lt;nhs-number&gt;
<br>&nbsp;&nbsp;&nbsp;Authorization = Bearer &lt;access token&gt;
<br>&nbsp;&nbsp;&nbsp;TraceID  =  &lt;yourRef&gt;
<!--</div>-->

<br>

**Parameters**

The patient's NHS Number. This must be a verified NHS Number.
- patient:identifier (required), type <a href='http://hl7.org/fhir/R4/search.html#token'>token</a>. 

<br>
<br>
{{render:fgm-is-interactions-get}}
<br>

**HTTP response and headers**
<!--<div style="width: 300px; border: 1px solid darkgrey; padding: 10px; width: 100%">-->
Content-Type = &lt;application/fhir+json&gt;<br>
Date             = &lt;servedDateTime&gt;<br>
<!--</div>-->

<br>

**HTTP response body**

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Record found       | SearchSet Bundle - {{pagelink:Home/Build/Examples/Example---FGM-flag-found.page.md}}|
| No record found       | SearchSet Bundle - {{pagelink:Home/Build/Examples/Example---FGM-flag-not-found.page.md}}|
| Error or validation failure      | OperationOutcome - {{pagelink:Home/Build/Errorhandling.page.md}}|

<br>

### Create an FGM indicator

<br>

**HTTP request and headers**
<!--<div style="width: 300px; border: 1px solid darkgrey; padding: 10px; width: 100%">-->
<strong><font color="#00008B">POST</font></strong> /Flag
<br>&nbsp;&nbsp;&nbsp;Authorization = Bearer &lt;access token&gt;
<br>&nbsp;&nbsp;&nbsp;TraceID  =  &lt;yourRef&gt;
<!--</div>-->

<br>

**Request body**

A FHIR Flag conforming to the UKCore-Flag profile. Values set as per {{pagelink:Home/Design/Data-mapping.page.md}}
- {{pagelink:Home/Build/Examples/Example---An-active-FGM-flag.page.md}} 

<br>
<br>
{{render:fgm-is-interactions-post}}
<br>

**HTTP response and headers**
<!--<div style="width: 300px; border: 1px solid darkgrey; padding: 10px; width: 100%">-->
Content-Type = &lt;application/fhir+json&gt;<br>
Date             = &lt;servedDateTime&gt;<br>
<!--</div>-->

<br>

**HTTP response body**

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Flag added       | Flag - {{pagelink:Home/Build/Examples/Example---An-active-FGM-flag.page.md}}|
| Error or validation failure      | OperationOutcome - {{pagelink:Home/Build/Errorhandling.page.md}}

<br>

### Remove an FGM indicator

<br>

**HTTP request and headers**
<!--<div style="width: 300px; border: 1px solid darkgrey; padding: 10px; width: 100%">-->
<strong><font color="#00008B">PUT</font></strong> /Flag/&lt;id&gt;
<br>&nbsp;&nbsp;&nbsp;Authorization = Bearer &lt;access token&gt;
<br>&nbsp;&nbsp;&nbsp;TraceID  =  &lt;yourRef&gt;
<!--</div>-->

<br>

**Parameters**

The id of the Flag resource being updated (marked as removed).
- id (required)

<br>

**Request body**

A FHIR Flag conforming to the UKCore-Flag profile. Values set as per {{pagelink:Home/Design/Data-mapping.page.md}}
- the id element value must be identical to the [id] in the URL
- the status must be set to either 'inactive' or 'entered-in-error'.
- {{pagelink:Home/FHIRAssets/AllAssets/Extension/Extension-England-FGMRemovalReason.page.md}} must be included. 
-  The Flag resource being updated (signified by [id]) must have a current server status of 'active'. No changes will be persisted to a Flag which has already been removed.
- The PUT interaction only supports updates to status and delete reason. Other fields should be supplied but will not be updated.
- {{pagelink:Home/Build/Examples/Example---A-removed-FGM-flag.page.md}}

<br>
<br>
{{render:fgm-is-interactions-put}}
<br>

**HTTP response and headers**
<!--<div style="width: 300px; border: 1px solid darkgrey; padding: 10px; width: 100%">-->
Content-Type = &lt;application/fhir+json&gt;<br>
Date             = &lt;servedDateTime&gt;<br>
<!--</div>-->

<br>

**HTTP response body**

| Outcome         | Response                       |
| ----------- | ------------------------  |
| Flag removed       | Flag - {{pagelink:Home/Build/Examples/Example---A-removed-FGM-flag.page.md}}|
| Error or validation failure      | OperationOutcome - {{pagelink:Home/Build/Errorhandling.page.md}}|

