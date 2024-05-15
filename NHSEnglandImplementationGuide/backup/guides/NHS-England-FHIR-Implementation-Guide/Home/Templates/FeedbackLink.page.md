<fql output="inline" delimiter="">
select
    Link: {
        text: 'Report issue for ' + %issue,
        href: 'https://simplifier.net/NHS-England-Implementation-Guide/' + %issue + '/~issues?level=File'
    }
group by Link
</fql>