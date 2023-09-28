## <code>{{page-title}}</code>

<div id="transpose">
@```
from
	NamingSystem
where
	id = 'readv2-namingsystem'
select
  Responsible_Organisation: responsible,
	Description: description
```
</div>
<br>

<div class="tab">
 <button class="tablinks active" onclick="openTab(event, 'Overview')">Overview</button>
   <button class="tablinks" onclick="openTab(event, 'Table View')">Table View</button>
   <button class="tablinks" onclick="openTab(event, 'XML View')">XML View</button>
  <button class="tablinks" onclick="openTab(event, 'JSON View')">JSON View</button>
</div>

<div id="Overview" class="tabcontent" style="display:block">
  <h3>Overview</h3>
{{render:http://read.info/readv2, snapshot}}
</div>

<div id="Table View" class="tabcontent">
  <h3>Table View</h3>
{{table:http://read.info/readv2, snapshot}}
</div>

<div id="XML View" class="tabcontent">
  <h3>XML View</h3>
{{xml:http://read.info/readv2, snapshot}}
</div>

<div id="JSON View" class="tabcontent">
  <h3>JSON View</h3>
{{json:http://read.info/readv2, snapshot}}
</div>

---