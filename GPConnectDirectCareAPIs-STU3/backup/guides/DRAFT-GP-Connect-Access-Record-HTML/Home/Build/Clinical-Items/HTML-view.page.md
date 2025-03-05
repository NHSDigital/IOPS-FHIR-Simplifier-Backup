## {{page-title}}

```html
<div>
   <h1>Clinical Items</h1>
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
   <table id="cli-tab">
      <thead>
         <tr>
            <th>Date</th>
            <th>Entry</th>
            <th>Details</th>
         </tr>
      </thead>
      <tbody>
         <tr>
            <!-- the <tr>...</tr> element will repeat for each clinical item-->
            <td class="date-column">$ item.date $</td>
            <td>$ item.entry $</td>
            <td>$ item.details $</td>
         </tr>
      </tbody>
   </table>
</div>
```