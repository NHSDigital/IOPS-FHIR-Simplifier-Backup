<fql output="inline" delimiter="">
select
    Link: {
        text: 'Report issue for ' + %issue,
        href: 'https://simplifier.net/NHS-Digital-FHIR-Genomics-Implementation-Guide/' + %issue + '/~issues?status=AllStatuses&level=File'
    }
group by Link
</fql>