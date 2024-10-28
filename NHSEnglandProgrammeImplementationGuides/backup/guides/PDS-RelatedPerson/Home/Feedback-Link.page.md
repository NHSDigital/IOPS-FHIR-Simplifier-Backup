<fql output="inline" delimiter="">
select
    Link: {
        text: 'Report issue for ' + %issue,
        href: 'https://simplifier.net/nhs-england-programme-implementation-guides/' + %issue + '/~issues?level=File'
    }
group by Link
</fql>