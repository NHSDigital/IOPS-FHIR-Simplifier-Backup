<div class="post-header">
   <h1 class="post-title-main">Clinical terminologies</h1>
</div>





<div class="post-content">

   
<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body"><b>Summary</b>:Brief guidance on how clinical terminologies are expected to be used within GP Connect</div>
   

   

    
    
<!-- this handles the automatic toc. use ## for subheads to auto-generate the on-page minitoc. if you use html tags, you must supply an ID for the heading element in order for it to appear in the minitoc. -->
<script>
$( document ).ready(function() {
  // Handler for .ready() called.

$('#toc').toc({ minimumHeaders: 0, listType: 'ul', showSpeed: 0, headers: 'h2,h3,h4' });

/* this offset helps account for the space taken up by the floating toolbar. */
$('#toc').on('click', 'a', function() {
  var target = $(this.getAttribute('href'))
    , scroll_target = target.offset().top

  $(window).scrollTop(scroll_target - 10);
  return false
})
  
});
</script>

<div id="toc"></div>

    

  <h2 id="terminology-and-classifications">Terminology and classifications</h2>

[NHS Digital Information Standards](https://digital.nhs.uk/services/terminology-and-classifications) are responsible for the UK management of <a href="https://digital.nhs.uk/services/terminology-and-classifications/snomed-ct" target="_blank">SNOMED CT</a>, <a href="https://digital.nhs.uk/services/terminology-and-classifications/read-codes" target="_blank">Read Codes</a> and other healthcare terminology products.

<p>They also maintain the <a href="http://www.nhsbsa.nhs.uk/1121.aspx" target="_blank">NHS Dictionary of Medicines and Devices (dm+d)</a> in partnership with the NHS Business Service Authority.</p>

<h3 id="snomed-ct-read2--ctv3-code-usage">SNOMED CT, READ2 &amp; CTV3 code usage</h3>

<p>GP Connect systems are expected to handle coded data as follows:</p>

<ul>
  <li>data originally entered into a system using the preferred system (that is, SNOMED CT)
    <ul>
      <li>SHALL be returned as SNOMED CT. The SNOMED CT DescriptionID should be included in addition to the ConceptID where available. The DescriptionID can convey a different meaning to the ConceptID due to the difference in the specific wording used for the two codes.</li>
      <li>if no suitable code exists in the value set (that is, if only text is available, then just text MAY be used)</li>
    </ul>
  </li>
  <li>data originally entered into a system using an alternate coding system (for example, READ2 or CTV3)
    <ul>
      <li>SHALL be returned in the code system it was originally entered in (for example, READ2 or CTV3) AND</li>
      <li>SHALL also be returned as a preferred code (that is, SNOMED CT) if a valid mapping/alternate code exists (for example, there is an NHS Digital assured READ2 or CTV3 to SNOMED CT mapping in place)</li>
    </ul>
  </li>
</ul>

<h4 id="assured-mappings">Assured mappings</h4>

<p><a href="https://isd.hscic.gov.uk/trud3/user/guest/group/2/pack/8" target="_blank">Assured mappings</a> can be found in the <strong>NHS Data Migration</strong> download.</p>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> Updated assured mappings are released every 6 months; suppliers are expected to update their systems in line with the timescales currently required under the GPSoC framework.</div>

<h3 id="case-sensitivity-of-terminologies">Case sensitivity of terminologies</h3>
<p><a href="https://www.hl7.org/fhir/STU3/terminologies.html#required" target="_blank">FHIR terminologies</a></p>

<p>Throughout this specification, coded values are always treated as a pair composed of ‘system’ and ‘code’, where the system is a URL that identifies the code system that defines the codes.</p>

<p><strong>Notes:</strong></p>
<ul>
  <li>system values are always case sensitive</li>
  <li>different code systems make their own rules as to whether the codes they define are case sensitive or not</li>
  <li>all the codes defined by FHIR itself are case sensitive and SHALL be used in the provided case (usually, but not always, lowercase)</li>
</ul>




    

</div>
