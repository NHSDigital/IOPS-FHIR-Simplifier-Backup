<div class="tab fhirTree">
 <button class="tablinks active" onclick="openTab(event, 'Tree View')">Profile </button>
 <!--
 <button class="tablinks" onclick="openTab(event, 'Differential')">Differential</button>
 -->
  <button class="tablinks" onclick="openTab(event, 'Examples')">Examples</button>
  <button class="tablinks mappings" onclick="openTab(event, 'Mappings')">Mappings</button>
</div>


<div id="Tree View" class="tabcontent expandedProfile" style="display:block">
{{tree,buttons}}
</div>

<!--
<div id="Differential" class="tabcontent">
    Differential from {{link}} <br>
    <br>
     {{tree, diff}}
</div>

    <div class="tab-content snippet">
        <div id="Profile" role="tabpanel" class="tab-pane active">
            <br />
            {{tree, snapshot}}
        </div>
        <div id="Differential" role="tabpanel" class="tab-pane">
         <br />
         Differential from {{link}} <br>
            <br />
            {{tree, diff}}
        </div>
        <div id="Dictionary" role="tabpanel" class="tab-pane">
            <br />
            {{dict, hybrid}}
        </div>
        
        <div id="Examples" role="tabpanel" class="tab-pane">
        </div>
        <div id="Mappings" role="tabpanel" class="tab-pane">
        </div>
    </div>
</div>
-->