## {{page-title}}

```html
<div>
   <h1>Immunisations</h1>
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
   <div class="exclusion-banner">
      <p>
         <!-- Exclusion banner -->
      </p>
   </div>
   <table id="imm-tab">
      <thead>
         <tr>
            <th>Date</th>
            <th>Vaccination</th>
            <th>Part</th>
            <th>Contents</th>
            <th>Details</th>
         </tr>
      </thead>
      <tbody>
         <tr>
            <!-- the <tr>...</tr> element will repeat for each immunisation-->
            <td class="date-column">${immunisation.date}</td>
            <td>${immunisation.vaccination}</td>
            <td>${immunisation.part}</td>
            <td>${immunisation.contents}</td>
            <td>${immunisation.details}</td>
         </tr>
      </tbody>
   </table>
</div>
```