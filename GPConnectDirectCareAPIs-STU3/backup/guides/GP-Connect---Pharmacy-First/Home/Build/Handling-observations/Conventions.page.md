## {{page-title}}

While the provider should make every effort to ensure they are providing accurate information, there are certain conventions that are preferred within GP practice which are shown hin the table below.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Note</b>: It is preferred that the value displayed to the user is <b>rounded up</b> if displaying to a decimal place that is less than the recorded value.
</div>

All units of measure use the {{pagelink:Home/FHIR-Assets/All-assets/Value-sets/Value-set--UCUM}} for vital-signs.

<table data-responsive class="nhsd-!t-margin-bottom-6 nhsd-!t-margin-top-6">
    <thead>
        <tr>
            <th data-no-sort>Observation</th>
            <th data-no-sort>Preferred unit of measure</th>
            <th data-no-sort>Display decimal places</th>
        </tr>
    </thead>
    <tbody>
        <!-- Height -->
        <tr>
            <td>Height</td>
            <td><code>cm</code> (centimeter)</td>
            <td>0 decimal places</td>
        </tr>
        <!-- Weight -->
        <tr>
            <td>Weight</td>
            <td><code>kg</code> (kilogram)</td>
            <td>1 decimal place</td>
        </tr>
        <!-- Pulse -->
        <tr>
            <td>Pulse</td>
            <td><code>{beats}/min</code> (beats per minute)</td>
            <td>0 decimal places</td>
        </tr>
        <!-- Blood pressure -->
        <tr>
            <td>Blood pressure</td>
            <td><code>[mmHg]</code> (millimeter of mercury)</td>
            <td>0 decimal places</td>
        </tr>
        <!-- Temperature -->
        <tr>
            <td>Temperature</td>
            <td><code>Cel</code> (Celsius)</td>
            <td>1 decimal place</td>
        </tr>
        <!-- Body Mass index -->
        <tr>
            <td>Body Mass Index (BMI)</td>
            <td><code>kg/m^2</code> (kilogram per meter squared)</td>
            <td>1 decimal place</td>
        </tr>
    </tbody>
</table>

---