## {{page-title}}

Providers must return all the columns as described in the table below, sorted by `Date` descending:

<div>
<table>
<thead>
  <tr class="header">
	<th style="width:5%">Order</th>
	<th style="width:23%">Name</th>
	<th style="width:58%">Description</th>
	<th style="width:14%">Value details</th>
  </tr>
 </thead>
  <tr>
    <td style="text-align:center">1</td>
    <td><code>Date</code> <em class="fa fa-sort-desc" aria-hidden="true"></em> </td>
    <td>The date of the observation</td>
    <td><code>dd-Mmm-yyyy</code></td>
  </tr> 
  <tr>
    <td style="text-align:center">2</td>
    <td><code>Entry</code></td>
    <td>A short human readable free-text title for the observation</td>
    <td><code>free-text</code></td>
  </tr>
  <tr>
    <td style="text-align:center">3</td>
    <td><code>Value</code></td>
	  <td>Value of the observation. As a minimum, this <strong>MUST</strong> include:
		<ul>
			<li>Value</li>
			<li>Value unit, where available</li>
		</ul>
	  </td>
    <td><code>free-text</code></td>
  </tr>
  <tr>
    <td style="text-align:center">4</td>
    <td><code>Range</code></td>
    <td>Range of the observation, where available. As a minimum, this <strong>MUST</strong> include:
		<ul>
			<li>Range</li>
			<li>Range unit, where available (unit <strong>MUST</strong> be included if it differs from the unit included in <code>Value</code>)</li>
		</ul>
	</td>
	<td><code>free-text</code></td>
  </tr>
  <tr>
    <td style="text-align:center">5</td>
    <td><code>Details</code></td>
    <td>Longer human readable details for the observation</td>
    <td><code>free-text</code></td>
  </tr>
</table>
</div>


{% include custominfocallout.html content="**Note:** All number formatting **MUST** follow the formatting applied in GP clinical supplier system providing the patient record." type="info" %}

{% include custominfocallout.html content="**Important:** GP principal suppliers have indicated this section will contain all clinical items that represent measurement data (for example, blood pressure, temperature, heart rate)." type="warning" %}