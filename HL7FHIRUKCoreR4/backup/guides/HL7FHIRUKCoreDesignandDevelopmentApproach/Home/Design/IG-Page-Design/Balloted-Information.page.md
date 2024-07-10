## Balloted Information

Where guidance has been added or changed between ballots, it SHALL be highlighted in green.

For tr, td, li elements, this is done by adding <code>class="balloted"</code>

For Extensions, Profiles, ValueSets, CodeSystems that have been ADDED, this is done by adding this to the top of the relevant page - this will turn the whole of that Extension, ValueSet, CodeSystem green, or if added to a Profile page, the whole page green.

~~~~html
<div id="newAsset" markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This [Asset Type] underwent Clinical and Technical Assurance during Sprint X. This is a new [Asset Type] added to UK Core, and should undergo review under Ballot Y.
</div>
~~~~

The same div, without the <code>id="newAsset"</code> can be used on a page to add a green banner to the page. This should be used on any guidance page that is not an asset, e.g. within CodeableConcept guidance.

<div markdown="span" class="alert alert-success" role="alert"><h4><i class="fa fa-star"></i> Important</h4>

This [Asset Type] underwent Clinical and Technical Assurance during Sprint X. This is a new [Asset Type] added to UK Core, and should undergo review under Ballot Y.
</div>

---