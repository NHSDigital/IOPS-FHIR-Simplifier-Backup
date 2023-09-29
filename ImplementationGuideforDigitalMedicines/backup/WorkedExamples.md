## {{page-title}}

### Example A

VTM = **Oxytetracycline** | `22969001`

Dose = **250 milligram**

#### Step 1: Get child products (VMPs and AMPs) of the VTM

There are five valid and available VMPs. None are flagged in a way that require additional AMPs to be listed.

<table data-responsive>
<thead>
<tr>
<th>dm+d concept</th>
<th>Product</th>
</tr>
</thead>
<tbody>
<tr>
<td>VMP</td>
<td>Oxytetracycline 100mg/5ml oral suspension</td>
</tr>
<tr>
<td>VMP</td>
<td>Oxytetracycline 125mg/5ml oral suspension</td>
</tr>
<tr>
<td>VMP</td>
<td>Oxytetracycline 250mg tablets</td>
</tr>
<tr>
<td>VMP</td>
<td>Oxytetracycline 250mg/5ml oral suspension</td>
</tr>
<tr>
<td>VMP</td>
<td>Oxytetracycline 500mg/5ml oral suspension</td>
</tr>
</tbody>
</table>

#### Step 2: Calculate the required quantity of each VMP to fulfil the requested dose

<table data-responsive>
<thead>
<tr>
<th>dm+d concept</th>
<th>Product</th>
<th>Quantity Calculation</th>
<th>Unit of Measure</th>
</tr>
</thead>
<tbody>
<tr>
<td>VMP</td>
<td>Oxytetracycline 100mg/5ml oral suspension</td>
<td><code>250 / (20/1) = 12.5</code></td>
<td>ml</td>
</tr>
<tr>
<td>VMP</td>
<td>Oxytetracycline 125mg/5ml oral suspension</td>
<td><code>250 / (25/1) = 10</code></td>
<td>ml</td>
</tr>
<tr>
<td>VMP</td>
<td>Oxytetracycline 250mg tablets</td>
<td><code>250 / (250) = 1</code></td>
<td>tablet</td>
</tr>
<tr>
<td>VMP</td>
<td>Oxytetracycline 250mg/5ml oral suspension</td>
<td><code>250 / (50) = 5</code></td>
<td>ml</td>
</tr>
<tr>
<td>VMP</td>
<td>Oxytetracycline 500mg/5ml oral suspension</td>
<td><code>250 / (100/1) = 2.5</code></td>
<td>ml</td>
</tr>
</tbody>
</table>

#### Step 3: Order the list of products in a clinically suitable order

<table data-responsive>
<thead>
<tr>
<th>Product</th>
<th>Quantity (to fulfil 250 milligrams)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Oxytetracycline 250mg tablets</td>
<td>1 tablet</td>
</tr>
<tr>
<td>Oxytetracycline 250mg/5ml oral suspension</td>
<td>5 ml</td>
</tr>
<tr>
<td>Oxytetracycline 125mg/5ml oral suspension</td>
<td>10 ml</td>
</tr>
<tr>
<td>Oxytetracycline 500mg/5ml oral suspension</td>
<td>2.5 ml</td>
</tr>
<tr>
<td>Oxytetracycline 100mg/5ml oral suspension</td>
<td>12.5 ml</td>
</tr>
</tbody>
</table>

---

### Example B

VTM = **Salbutamol** | `91143003`

Dose = **200 micrograms**

Route = **Inhalation** | `18679011000001101`

#### Step 1: Get child products (VMPs and AMPs) of the VTM

There are two valid and available VMPs, but both are flagged as `Caution - AMP level prescribing advised` so we also query for valid and available AMPs.

<table data-responsive>
<thead>
<tr>
<th>dm+d concept</th>
<th>Product</th>
</tr>
</thead>
<tbody>
<tr><td>VMP</td><td>Salbutamol 100micrograms/dose breath actuated inhaler CFC free</td></tr>
<tr><td>-- AMP</td><td>Airomir 100micrograms/dose Autohaler (Teva UK Ltd)</td></tr>
<tr><td>-- AMP</td><td>Salamol 100micrograms/dose Easi-Breathe inhaler (CST Pharma Ltd)</td></tr>
<tr><td>-- AMP</td><td>Salamol 100micrograms/dose Easi-Breathe inhaler (Teva UK Ltd)</td></tr>
<tr><td>VMP</td><td>Salbutamol 100micrograms/dose inhaler CFC free</td></tr>
<tr><td>-- AMP</td><td>Airomir 100micrograms/dose inhaler (Teva UK Ltd)</td></tr>
<tr><td>-- AMP</td><td>Salamol 100micrograms/dose inhaler CFC free (Teva UK Ltd)</td></tr>
<tr><td>--AMP</td><td>Ventolin 100micrograms/dose Evohaler (GlaxoSmithKline UK Ltd)</td></tr>
</tbody>
</table>

#### Step 2: Calculate the required quantity of each VMP to fulfil the requested dose

<table data-responsive>
<thead>
<tr>
<th>dm+d concept</th>
<th>Product</th>
<th>Quantity Calculation</th>
<th>Unit of Measure</th>
</tr>
</thead>
<tbody>
<tr>
<td>VMP</td>
<td>Salbutamol 100micrograms/dose breath actuated inhaler CFC free</td>
<td><code>200 / (100) = 2</code></td>
<td>dose</td>
</tr>
<tr><td>-- AMP</td><td>Airomir 100micrograms/dose Autohaler (Teva UK Ltd)</td>
<td><code>200 / (100) = 2</code></td>
<td>dose</td>
</tr>
<tr><td>-- AMP</td><td>Salamol 100micrograms/dose Easi-Breathe inhaler (CST Pharma Ltd)</td>
<td><code>200 / (100) = 2</code></td>
<td>dose</td>
</tr>
<tr><td>-- AMP</td><td>Salamol 100micrograms/dose Easi-Breathe inhaler (Teva UK Ltd)</td>
<td><code>200 / (100) = 2</code></td>
<td>dose</td>
</tr>
<tr><td>VMP</td><td>Salbutamol 100micrograms/dose inhaler CFC free</td>
<td><code>200 / (100) = 2</code></td>
<td>dose</td>
</tr>
<tr><td>-- AMP</td><td>Airomir 100micrograms/dose inhaler (Teva UK Ltd)</td>
<td><code>200 / (100) = 2</code></td>
<td>dose</td>
</tr>
<tr><td>-- AMP</td><td>Salamol 100micrograms/dose inhaler CFC free (Teva UK Ltd)</td>
<td><code>200 / (100) = 2</code></td>
<td>dose</td>
</tr>
<tr><td>--AMP</td><td>Ventolin 100micrograms/dose Evohaler (GlaxoSmithKline UK Ltd)</td>
<td><code>200 / (100) = 2</code></td>
<td>dose</td>
</tr>
</tbody>
</table>

#### Step 3: Order the list of products in a clinically suitable order

As all products can be used with the same quantity, the order could be alphabetical or ordered as per any local formulary.

<table data-responsive>
<thead>
<tr>
<th>Product</th>
<th>Quantity (to fulfil 200 micrograms)</th>
</tr>
</thead>
<tbody>
<tr>
<td>Salbutamol 100micrograms/dose breath actuated inhaler CFC free<br/><strong>Note:</strong> <code>Caution - AMP level prescribing advised</code></td>
<td>2 dose</td>
</tr>
<tr>
<td>Airomir 100micrograms/dose Autohaler (Teva UK Ltd)</td>
<td>2 dose</td>
</tr>
<tr>
<td>Salamol 100micrograms/dose Easi-Breathe inhaler (CST Pharma Ltd)</td>
<td>2 dose</td>
</tr>
<tr>
<td>Salamol 100micrograms/dose Easi-Breathe inhaler (Teva UK Ltd)</td>
<td>2 dose</td>
</tr>
<tr>
<td>Salbutamol 100micrograms/dose inhaler CFC free<br/><strong>Note:</strong> <code>Caution - AMP level prescribing advised</code></td>
<td>2 dose</td>
</tr>
<tr>
<td>Airomir 100micrograms/dose inhaler (Teva UK Ltd)</td>
<td>2 dose</td>
</tr>
<tr>
<td>Salamol 100micrograms/dose inhaler CFC free (Teva UK Ltd)</td>
<td>2 dose</td>
</tr>
<tr>
<td>Ventolin 100micrograms/dose Evohaler (GlaxoSmithKline UK Ltd)</td>
<td>2 dose</td>
</tr>
</tbody>
</table>

---
