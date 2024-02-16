## {{page-title}}

  <div markdown="span" class="alert alert-warning" role="alert"><i class="fa fa-warning"></i><b> Important:</b> This page is under development by NHS England</div>

This page gives a link to download the FHIR assets as a downloadable package. It may be specific to the specification or be a snapshot of the UK Core FHIR assets.

This Implementation guide hdepends upon the following guides:

<fql>
from
	ImplementationGuide
	where url='https://fhir.nhs.uk/England/ImplmentationGuide/England-ImplementationGuide-ODS'
for dependsOn
where id != 'hl7tx' and id != 'hl7ext'
select
	Guide_URL:uri,
  Guide_Version:version,
  NPM:packageId
</fql>