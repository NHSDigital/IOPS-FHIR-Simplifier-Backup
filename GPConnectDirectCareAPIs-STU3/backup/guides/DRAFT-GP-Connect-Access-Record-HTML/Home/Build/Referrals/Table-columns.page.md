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
    <td><code>Date</code> <em class="fa fa-sort-desc" aria-hidden="true"></em></td>
    <td>The date of the referral</td>
    <td><code>dd-Mmm-yyyy</code></td>
  </tr> 
  <tr>
    <td style="text-align:center">2</td>
    <td><code>From</code></td>
    <td>Practitioner or Organisation referred from</td>
    <td><code>free-text</code></td>
  </tr>
  <tr>
    <td style="text-align:center">3</td>
    <td><code>To</code></td>
    <td>Practitioner or Organisation referred to </td>
    <td><code>free-text</code></td>
  </tr>
  <tr>
    <td style="text-align:center">4</td>
    <td><code>Priority</code></td>
    <td>The priority of the referral</td>
    <td><code>free-text</code></td>
  </tr>
  <tr>
    <td style="text-align:center">5</td>
    <td><code>Details</code></td>
    <td>Longer human readable details for the referral
		<ul>
			<li>This <strong>MUST</strong> include all clinically relevant information about the referral which is not included in the other columns</li>
			<li>This <strong>MUST</strong> include the original term text for the main coded item describing the referral, which <strong>MUST</strong> be the first item</li>
			<li>Any additional information, such as the free text description of the referral, <strong>MUST</strong> be separated from the original clinical term by a new line</li>
			<li>A label <strong>SHOULD</strong> preface additional information where necessary for reliable interpretation of the information</li>
		</ul>
	</td>
	<td><code>free-text</code></td>
  </tr>
</table>
</div>