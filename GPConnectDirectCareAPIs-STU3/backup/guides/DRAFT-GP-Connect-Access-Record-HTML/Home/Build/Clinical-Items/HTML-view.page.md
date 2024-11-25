## {{page-title}}

```
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
            <td class="date-column">{ {item.date} }</td>
            <td>{ {item.entry} }</td>
            <td>{ {item.details} }</td>
         </tr>
      </tbody>
   </table>
</div>
```
<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
        <i class="fas fa-exclamation-circle text-primary"></i> <b>Note:</b> In the example above, a space has been added into each pair of brackets enclosing a placeholder (e.g. <code>{ {item.date} }</code>). These spaces will need removing in the actual implementation.
</div>