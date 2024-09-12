<!-- This template is used in the Profile, Extension, CodeSystems and ValueSets templates to add a link in the render to the relevant issues page. Add the project into the 'href' below, e.g. NHS-England-Programme-Implementation-Guides. This does not need to be added to any page -->

<fql output="inline" delimiter="">
select
    Link: {
        text: 'Report issue for ' + %issue,
        href: 'https://simplifier.net/[project]/' + %issue + '/~issues?level=File'
    }
group by Link
</fql>