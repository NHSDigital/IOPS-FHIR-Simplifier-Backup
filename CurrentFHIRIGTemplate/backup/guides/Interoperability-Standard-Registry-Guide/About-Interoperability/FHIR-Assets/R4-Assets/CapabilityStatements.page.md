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

    
## CapabilityStatements

<div class="status-container">
<ul>

<li class="nhsengland"><a href="https://simplifier.net/nhs-england-implementation-guide/apim-conformance">apim-conformance</a>
  1.0.0
  2022-12-16T00:00:00+00:00
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/England-FHIRExamples-Conformance">England-FHIRExamples-Conformance</a>
  3.2.0
  2022-12-16T00:00:00+00:00
  <span class="status active">active</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/England-Healthcare-Worker-Requirements">England-Healthcare-Worker-Requirements</a>
  0.0.1-current
  2024-10-08
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/England-MCED-Requirements">England-MCED-Requirements</a>
  0.0.1
  2024-01-23
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/CapabilityStatement-England-NationalProxyRequirements">CapabilityStatement-England-NationalProxyRequirements</a>
  0.0.1-current
  2024-10-08
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/England-ODS-Requirements">England-ODS-Requirements</a>
  0.0.5
  2024-09-17
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/CapabilityStatement-England-PDSRelatedPersonRequirements">CapabilityStatement-England-PDSRelatedPersonRequirements</a>
  0.0.1-current
  2024-10-08
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/England-Pathology-Requirements">England-Pathology-Requirements</a>
  0.0.2
  2024-03-20
  <span class="status draft">draft</span>
</li>

<li class="nhsengland"><a href="https://simplifier.net/NHS-England-Programme-Implementation-Guides/England-PatientFlag-Server-Requirements">England-PatientFlag-Server-Requirements</a>
  0.1.0
  2024-09-20
  <span class="status draft">draft</span>
</li>

<li class="ukcore"><a href="https://simplifier.net/HL7FHIRUKCoreR4/apim-conformance">apim-conformance</a>
  3.2.0
  2022-12-16T00:00:00+00:00
  <span class="status active">active</span>
</li>

</ul></div><br><br>

---


