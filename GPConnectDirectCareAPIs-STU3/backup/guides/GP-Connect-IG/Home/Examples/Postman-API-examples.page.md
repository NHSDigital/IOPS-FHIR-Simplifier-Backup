<div class="post-header">
   <h1 class="post-title-main">Postman API examples</h1>
</div>

<div class="post-content">
   
<div class="summary"><b>Summary: </b>API documentation for the GP Connect FHIR&reg; API</div>
<br>

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
   

<h2 id="api-examples-using-postman">API examples using Postman</h2>


<p>Download the <a href="https://www.getpostman.com/" target="_blank" class="no_icon">Postman</a> App and import our Postman GP Connect examples collection.</p>

<h2 id="try-now">Try now</h2>


Visit the [GP Connect Demonstrator site and import our Postman samples]( https://orange.testlab.nhs.uk/index.html#postman-samples)

{{render:Postman Find a patient.png}}





    

</div>


</div>
<!-- /.row -->
</div>
<!-- /.container -->
    </div>

<!-- END FROM GITHUB TEMPLATE -->
<!--end apicontent--></div></div></div>
</div><!--end main_content-->
</div><!-- end main -->
