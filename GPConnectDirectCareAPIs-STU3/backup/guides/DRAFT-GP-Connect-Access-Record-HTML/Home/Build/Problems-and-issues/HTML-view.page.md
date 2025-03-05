## {{page-title}}

```html
<div>
   <h1>Problems and Issues</h1>
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
      <h2>Active Problems and Issues</h2>
      <div class="content-banner">
         <p>
            <!-- Content banner -->
         </p>
      </div>
      <div class="date-banner">
         <p>
            <!-- Date banner -->
         </p>
      </div>
      <div class="exclusion-banner">
         <p>
            <!-- Exclusion banner -->
         </p>
      </div>
      <table id="prb-tab-act">
         <thead>
            <tr>
               <th>Start Date</th>
               <th>Entry</th>
               <th>Significance</th>
               <th>Details</th>
            </tr>
         </thead>
         <tbody>
            <tr>
               <!-- the <tr>...</tr> element will repeat for each active problem and issue-->
               <td class="date-column">$ problemissue.startdate $</td>
               <td>$ problemissue.entry $</td>
               <td>$ problemissue.significance $</td>
               <td>$ problemissue.details $</td>
            </tr>
         </tbody>
      </table>
   </div>
   <div>
      <h2>Major Inactive Problems and Issues</h2>
      <div class="content-banner">
         <p>
            <!-- Content banner -->
         </p>
      </div>
      <div class="date-banner">
         <p>
            <!-- Date banner -->
         </p>
      </div>
      <div class="exclusion-banner">
         <p>
            <!-- Exclusion banner -->
         </p>
      </div>
      <table id="prb-tab-majinact">
         <thead>
            <tr>
               <th>Start Date</th>
               <th>End Date</th>
               <th>Entry</th>
               <th>Significance</th>
               <th>Details</th>
            </tr>
         </thead>
         <tbody>
            <tr>
               <!-- the <tr>...</tr> element will repeat for each major inactive problem and issue-->
               <td class="date-column">$ problemissue.startdate $</td>
               <td class="date-column">$ problemissue.enddate $</td>
               <td>$ problemissue.entry $</td>
               <td>$ problemissue.significance $</td>
               <td>$ problemissue.details $</td>
            </tr>
         </tbody>
      </table>
   </div>
   <div>
      <h2>Other Inactive Problems and Issues</h2>
      <div class="content-banner">
         <p>
            <!-- Content banner -->
         </p>
      </div>
      <div class="date-banner">
         <p>
            <!-- Date banner -->
         </p>
      </div>
      <div class="exclusion-banner">
         <p>
            <!-- Exclusion banner -->
         </p>
      </div>
      <table id="prb-tab-othinact">
         <thead>
            <tr>
               <th>Start Date</th>
               <th>End Date</th>
               <th>Entry</th>
               <th>Significance</th>
               <th>Details</th>
            </tr>
         </thead>
         <tbody>
            <tr>
               <!-- the <tr>...</tr> element will repeat for each other inactive problem and issue-->
               <td class="date-column">$ problemissue.startdate $</td>
               <td class="date-column">$ problemissue.enddate $</td>
               <td>$ problemissue.entry $</td>
               <td>$ problemissue.significance $</td>
               <td>$ problemissue.details $</td>
            </tr>
         </tbody>
      </table>
   </div>
</div>
```