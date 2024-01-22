<fql output="inline">
from StructureDefinition
where url=%subject
select
        Link: {
            text: 'Report issue for '+%issue,
            href: 'https://simplifier.net/HL7FHIRUKCoreR4/'+%issue+'/~issues?level=File'}
</fql>