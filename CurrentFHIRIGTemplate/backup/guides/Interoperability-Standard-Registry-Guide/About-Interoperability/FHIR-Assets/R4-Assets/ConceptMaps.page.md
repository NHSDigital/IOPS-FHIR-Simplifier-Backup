<label>
    <input type="checkbox" id="ukcore-checkbox" checked>
    Show UKCore Items
    </label>
    <br>
    <label>
    <input type="checkbox" id="nhsengland-checkbox" checked>
    Show NHSEngland Items
    </label>

    
<script>
    const ukcoreCheckbox = document.getElementById('ukcore-checkbox');
    const nhsenglandCheckbox = document.getElementById('nhsengland-checkbox');

    ukcoreCheckbox.addEventListener('change', function() {
        const ukcoreItems = document.querySelectorAll('.ukcore');
        ukcoreItems.forEach(item => {
        if (ukcoreCheckbox.checked) {
            item.classList.remove('hidden');
        } else {
            item.classList.add('hidden');
        }
        });
    });

    nhsenglandCheckbox.addEventListener('change', function() {
        const nhsenglandItems = document.querySelectorAll('.nhsengland');
        nhsenglandItems.forEach(item => {
        if (nhsenglandCheckbox.checked) {
            item.classList.remove('hidden');
        } else {
            item.classList.add('hidden');
        }
        });
    });
    </script>

    
## ConceptMaps

<div class="status-container">
<ul>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-AdministrativeGender">UKCore-AdministrativeGender</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-ConditionEpisodicity">UKCore-ConditionEpisodicity</a>
  2.0.0
  2022-12-16
  <span class="status retired">retired</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/UKCore-MaritalStatus">UKCore-MaritalStatus</a>
  2.0.0
  2021-09-10
  <span class="status retired">retired</span>
</li>

</ul></div><br><br>

---


