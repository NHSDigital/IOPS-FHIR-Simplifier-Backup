## {{page-title}}
<div class="post-header">
   <h1 class="post-title-main">GP Connect Demonstrator</h1>
</div>





<div class="post-content">

   
<div class="summary"><b>Summary</b>Consumer system demonstrator and provider API reference implementation</div>
   

   

    
    
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

    

  <h2 id="try-now">Try now</h2>

<blockquote>
  <p>Go to the <a href="https://orange.testlab.nhs.uk/" target="_blank">GP Connect Demonstrator</a> website now!</p>
</blockquote>

<div class="alert alert-warning" role="alert"><i class="fa fa-warning"></i> <b>Important:</b> Data held in the GP Connect Demonstrator is reset each night to allow for easier testing. Please refer to the Demonstrator’s in-built help for further details.</div>

<h2 id="overview">Overview</h2>

<p>The GP Connect Demonstrator is a mock GP Connect consumer system, a reference implementation of the GP Connect provider APIs, and development and test tools (<a href="system_swagger.html">interactive documentation</a> and <a href="system_reference_postman.html">samples</a> for the Postman application).</p>

<p>Please view the <a href="https://orange.testlab.nhs.uk/" target="_blank">GP Connect Demonstrator</a> website for more information.</p>

<p><img src="images/systems/demonstrator-high-level-overview.png" alt="GP Connect Demonstrator high level overview" /></p>

<h2 id="example-screenshots-from-the-mock-consumer-system">Example screenshots from the mock consumer system</h2>

<p>The following screen shows part of the Appointment Management functionality of the mock consumer system application:</p>

<p><img src="images/systems/GP Connect Demonstrator Patient Summary.png" alt="GP Connect Demonstrator Patient Summary" /></p>

<h2 id="source-code">Source code</h2>

<p>Download the source code from the
<a href="https://github.com/nhsconnect/gpconnect-demonstrator" target="_blank">GP Connect Demonstrator Github repository</a>.</p>




    

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
