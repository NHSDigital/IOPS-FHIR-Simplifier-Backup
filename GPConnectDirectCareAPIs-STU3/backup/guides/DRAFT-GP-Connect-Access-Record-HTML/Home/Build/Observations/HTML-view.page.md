## {{page-title}}

```html
<div>
   <h1>Observations</h1>
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
   <table id="obs-tab">
      <thead>
         <tr>
            <th>Date</th>
            <th>Entry</th>
            <th>Value</th>
            <th>Details</th>
         </tr>
      </thead>
      <tbody>
         <tr>
            <!-- the <tr>...</tr> element will repeat for each observation-->
            <td class="date-column">${observation.date}</td>
            <td>${observation.entry}</td>
            <td>${observation.value}</td>
            <td>${observation.details}</td>
         </tr>
      </tbody>
   </table>
</div>
```