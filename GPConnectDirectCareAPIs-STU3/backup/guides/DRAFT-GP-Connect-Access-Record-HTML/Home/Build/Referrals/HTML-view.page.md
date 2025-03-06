## {{page-title}}

```html
<div>
   <h1>Referrals</h1>
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
   <table id="ref-tab">
      <thead>
         <tr>
            <th>Date</th>
            <th>From</th>
            <th>To</th>
            <th>Priority</th>
            <th>Details</th>
         </tr>
      </thead>
      <tbody>
         <tr>
            <!-- the <tr>...</tr> element will repeat for each referral-->
            <td class="date-column">${referral.date}</td>
            <td>${referral.from}</td>
            <td>${referral.to}</td>
            <td>${referral.priority}</td>
            <td>${referral.details}</td>
         </tr>
      </tbody>
   </table>
</div>
```