## {{page-title}}

```html
<div>
   <h1>Encounters</h1>
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
   <table id="enc-tab">
      <thead>
         <tr>
            <th>Date</th>
            <th>Title</th>
            <th>Details</th>
         </tr>
      </thead>
      <tbody>
         <tr>
            <!-- the <tr>...</tr> element will repeat for each encounter-->
            <td class="date-column">$ encounter.date $</td>
            <td>$ encounter.entry $</td>
            <td>$ encounter.details $</td>
         </tr>
      </tbody>
   </table>
</div>
</div>
```