## {{page-title}}

There are two styles of HTML view: pages where multiple tables are provided in the same HTML view page and those where a single table is returned. Sections with multiple tables are subdivided into subsections.

### HTML views with a single table

HTML views with a single table and hence a single section are:

**Encounters**, **Clinical Items**, **Administrative Items**, **Observations**, **Referrals**, **Immunisations**.

These views **MUST** have the following structure:

- Section title
- GP transfer banner
- Content banner (if applicable)
- Date banner (if applicable: section date range applied)
- Exclusion banner (if applicable: to indicate excluded items)
- Table

### HTML views with multiple tables

HTML views with multiple tables and hence multiple subsections are:

**Summary**, **Problems and issues**, **Allergies and adverse reactions**, and **Medications**.

These views **MUST** have the following structure:

- Section title
- GP transfer banner
- Content banner (if applicable)
- Subsection (repeated for each subsection)
    - Subsection title (for example, Current Medications)
    - Subsection content banner (if applicable)
    - Date banner (if applicable: subsection date range applied)
    - Exclusion banner (if applicable, to indicate excluded items)
    - Table

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
        <i class="fas fa-exclamation-circle text-primary"></i> <b>Note:</b> This layout does not fully apply to the Summary HTML view. Subsection content banner messages <b>MUST</b> be included only when associated with table content visible in the Summary view. See Summary HTML view.
</div>

### Single table example

```html
<div>
  <h1>Encounters</h1>
	
  <div class="gptransfer-banner">
    <p><!-- GP transfer banner --></p>
  </div>
	
  <div class="content-banner">
    <p><!-- Content banner --></p>
  </div>
  
  <div class="date-banner">
    <p><!-- Date banner --></p>
  </div>
  
  <div class="exclusion-banner">
    <p><!-- Exclusion banner --></p>
  </div>
  
  <table id="enc-tab">
    <!-- table data -->
  </table>
</div>
```
### Multiple table example

```html
<div>
  <h1>Problems and Issues</h1>
   
  <div class="gptransfer-banner">
    <p><!-- GP transfer banner --></p>
  </div>
	
  <div class="content-banner">
    <p><!-- Content banner --></p>
  </div>

  <div>
    <h2>Active Problems and Issues</h2>
	
	<div class="content-banner">
	  <p><!-- Content banner --></p>
	</div>
    
	<div class="date-banner">
	  <p><!-- Date banner --></p>
	</div>
    
	<div class="exclusion-banner">
	  <p><!-- Exclusion banner --></p>
	</div>
    
	<table id="prb-tab-act">
	  <!-- table data -->
	</table>
  </div>
  
  <div>
    <h2>Major Inactive Problems and Issues</h2>

	<div class="content-banner">
	  <p><!-- Content banner --></p>
	</div>
    
	<div class="date-banner">
	  <p><!-- Date banner --></p>
	</div>
    
	<div class="exclusion-banner">
	  <p><!-- Exclusion banner --></p>
	</div>
    
	<table id="prb-tab-majinact">
	  <!-- table data -->
	</table>
  </div>
	
  <div>
    <h2>Other Inactive Problems and Issues</h2>

	<div class="content-banner">
	  <p><!-- Content banner --></p>
	</div>
    
	<div class="date-banner">
	  <p><!-- Date banner --></p>
	</div>
    
	<div class="exclusion-banner">
	  <p><!-- Exclusion banner --></p>
	</div>
    
	<table id="prb-tab-othinact">
	  <!-- table data -->
	</table>
  </div>
</div>
```
