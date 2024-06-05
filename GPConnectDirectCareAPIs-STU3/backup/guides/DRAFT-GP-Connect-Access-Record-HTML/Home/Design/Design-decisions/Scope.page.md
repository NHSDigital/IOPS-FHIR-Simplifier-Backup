## {{page-title}}

### Scope of HTML view
What is the scope of what views we’re aiming to deliver?
- <span class="label label-info">DECISION</span> initially a set of views covering the majority of the primary care record have been included based on workshops with principal suppliers to agree how the data can be most sensible sectioned   
    
    - some desirable headings such as Procedures, Diagnosis, Symptoms have been amalgamated into the ‘Clinical Items’ heading because the underlying data structure of the GP systems cannot reliably extract these coded elements
- <span class="label label-info">DECISION</span> the scope of the views will be reviewed and added to as future versions of the API are produced
- <span class="label label-info">DECISION</span> provider **MUST** return minimal patient resource(s)
- <span class="label label-info">DECISION</span> remove the structured clinical data from the bundle until Access Record Structured delivery

### View non-retrieval
Potential grounds for not returning an HTML view?
- <span class="label label-info">DECISION</span> technical constraints 
    - generation from structured FHIR® resources
    - can’t safely retrieve from GP system
- <span class="label label-info">DECISION</span> information governance 
    - data sharing agreement not in place
    - patient dissent to record sharing
- <span class="label label-info">DECISION</span> PDS status 
    - corrupt record, etc.