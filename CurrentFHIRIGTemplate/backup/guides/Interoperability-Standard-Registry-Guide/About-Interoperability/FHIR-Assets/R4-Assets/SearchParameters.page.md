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

    
## SearchParameters

<div class="status-container">
<ul>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/England-Extension-OrganisationRole-ActiveRoleCode">England-Extension-OrganisationRole-ActiveRoleCode</a>
  0.0.2
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/England-Extension-OrganisationRole-RoleCode">England-Extension-OrganisationRole-RoleCode</a>
  0.0.2
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/England-Extension-TypedDateTime-LastChangeDate">England-Extension-TypedDateTime-LastChangeDate</a>
  0.0.2
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/England-FlagCategory">England-FlagCategory</a>
  0.4.0
  2024-02-14
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/England-FlagCode">England-FlagCode</a>
  0.1.0
  2024-02-14
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/England-FlagDetail">England-FlagDetail</a>
  0.4.0
  2024-02-14
  <span class="status active">active</span>
</li>

</ul></div><br><br>

---


