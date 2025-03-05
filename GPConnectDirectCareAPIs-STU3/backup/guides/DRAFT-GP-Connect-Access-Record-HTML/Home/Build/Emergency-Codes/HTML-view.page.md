## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body"><i class="fa fa-exclamation-circle"></i><b>Information: </b>The table id ‘cli-tab’ has been re-used to avoid any negative consumer css impact.</div>

```html
<div>
   <h1>Emergency Codes</h1>
   <div class="content-banner">
      <p>
         <!-- Content banner -->
      </p>
   </div>
   <table id="cli-tab">
      <thead>
         <tr>
            <th>Date</th>
            <th>Entry</th>
            <th>Details</th>
            <th>Location of further information</th>
         </tr>
      </thead>
      <tbody>
         <tr>
            <!-- the <tr>...</tr> element will repeat for each emergency code configured-->
            <td class="date-column">$ emergency.startdate $</td>
            <td>$ emergency.entry $</td>
            <td>$ emergency.details $</td>
            <td>$ emergency.location $</td>
         </tr>
      </tbody>
   </table>
</div>
```