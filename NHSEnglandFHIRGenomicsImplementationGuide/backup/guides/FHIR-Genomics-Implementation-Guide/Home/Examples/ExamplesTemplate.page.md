<div class="tab">
    <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON</button>
    <button class="tablinks" onclick="openTab(event, 'XML View')">XML</button>
    <button class="tablinks active" onclick="openTab(event, 'Tree View')">Tree</button>
    <button class="tablinks feedback" onclick="openTab(event, 'Feedback')">Feedback</button>
     
   </div>
   
   <div id="JSON View" class="tabcontent" style="display:block">
     <h3>JSON</h3>
   {{json}}
   </div>
   
   <div id="XML View" class="tabcontent">
     <h3>XML</h3>
   {{xml}}
   </div>
   
   <div id="Tree View" class="tabcontent">
     <h3>Tree</h3>
   {{tree}}
   </div>