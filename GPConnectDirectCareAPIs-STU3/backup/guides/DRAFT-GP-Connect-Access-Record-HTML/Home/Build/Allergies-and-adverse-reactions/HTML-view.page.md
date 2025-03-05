## {{page-title}}

```html
<div>
   <h1>Allergies and Adverse Reactions</h1>
   <div class="gptransfer-banner">
      <p>
         <!-- GP transfer banner -->
      </p>
   </div>
   <div class="content-banner">
      <p>
         <!-- Content banner -->
      </p>
   </div>
   <div>
      <h2>Current Allergies and Adverse Reactions</h2>
      <div class="content-banner">
         <p>
            <!-- Content banner -->
         </p>
      </div>
      <div class="exclusion-banner">
         <p>
            <!-- Exclusion banner -->
         </p>
      </div>
      <table>
         <thead>
            <tr>
               <th>Start Date</th>
               <th>Details</th>
            </tr>
         </thead>
         <tbody>
            <tr>
               <!-- the <tr>...</tr> element will repeat for each current allergy and adverse reaction-->
               <td class="date-column">$ allergyadversereaction.startdate $</td>
               <td>$ allergyadversereaction.details $</td>
            </tr>
         </tbody>
      </table>
   </div>
   <div>
      <h2>Historical Allergies and Adverse Reactions</h2>
      <div class="content-banner">
         <p>
            <!-- Content banner -->
         </p>
      </div> 
	  <div class="exclusion-banner">
         <p>
            <!-- Exclusion banner -->
         </p>
      </div>
      <table>
         <thead>
            <tr>
               <th>Start Date</th>
               <th>End Date</th>
               <th>Details</th>
            </tr>
         </thead>
         <tbody>
            <tr>
               <!-- the <tr>...</tr> element will repeat for each historical allergy and adverse reaction-->
               <td class="date-column">$ allergyadversereaction.startdate $</td>
               <td class="date-column">$ allergyadversereaction.enddate $</td>
               <td>$ allergyadversereaction.details $</td>
            </tr>
         </tbody>
      </table>
   </div>
</div>
```