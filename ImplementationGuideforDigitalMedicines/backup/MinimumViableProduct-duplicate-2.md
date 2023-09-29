## Minimum Viable Product

Links to the definitions of `MedicationDispense` covered within this guidance:

- [R4 Resource](https://www.hl7.org/fhir/medicationdispense.html)
- [UK Core Resource](https://simplifier.net/ukcore-v2/ukcoremedicationdispense)

<table data-responsive>
    <thead>
        <tr>
            <th>Element</th>
            <th data-no-sort>MVP</th>
            <th data-no-sort>R4</th>
            <th data-no-sort>UK Core</th>
        </tr>
    </thead>
    <tbody>
        <!-- identifier -->
        <tr>
            <td>
                <a href="#Elementidentifier2">identifier</a>
            </td>
            <td>
                <span class="mro-circle mandatory" title="Mandatory"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- partOf -->
        <tr>
            <td>
                <a href="#ElementpartOf">partOf</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- status -->
        <tr>
            <td>
                <a href="#Elementstatus2">status</a>
            </td>
            <td>
                <span class="mro-circle mandatory" title="Mandatory"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- statusReason -->
        <tr>
            <td>
                <a href="#ElementstatusReason2">statusReason</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- category -->
        <tr>
            <td>
                <a href="#Elementcategory2">category</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- medication[x] -->
        <tr>
            <td>
                <a href="#Elementmedicationx2">medication[x]</a>
            </td>
            <td>
                <span class="mro-circle mandatory" title="Mandatory"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- subject -->
        <tr>
            <td>
                <a href="#Elementsubject2">subject</a>
            </td>
            <td>
                <span class="mro-circle mandatory" title="Mandatory"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- context -->
        <tr>
            <td>
                <a href="#Elementcontext">context</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- supportingInformation -->
        <tr>
            <td>
                <a href="#ElementsupportingInformation2">supportingInformation</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- performer -->
        <tr>
            <td>
                <a href="#Elementperformer">performer</a>
            </td>
            <td>
                <span class="mro-circle mandatory" title="Mandatory"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- location -->
        <tr>
            <td>
                <a href="#Elementlocation">location</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- authorizingPrescription -->
        <tr>
            <td>
                <a href="#ElementauthorizingPrescription">authorizingPrescription</a>
            </td>
            <td>
                <span class="mro-circle required" title="Required"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- type -->
        <tr>
            <td>
                <a href="#Elementtype">type</a>
            </td>
            <td>
                <span class="mro-circle required" title="Required"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- quantity -->
        <tr>
            <td>
                <a href="#Elementquantity">quantity</a>
            </td>
            <td>
                <span class="mro-circle mandatory" title="Mandatory"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- daysSupply -->
        <tr>
            <td>
                <a href="#ElementdaysSupply">daysSupply</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- whenPrepared -->
        <tr>
            <td>
                <a href="#ElementwhenPrepared">whenPrepared</a>
            </td>
            <td>
                <span class="mro-circle mandatory" title="Mandatory"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- whenHandedOver -->
        <tr>
            <td>
                <a href="#ElementwhenHandedOver">whenHandedOver</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- destination -->
        <tr>
            <td>
                <a href="#Elementdestination">destination</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- receiver -->
        <tr>
            <td>
                <a href="#Elementreceiver">receiver</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- note -->
        <tr>
            <td>
                <a href="#Elementnote2">note</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- dosageInstruction -->
        <tr>
            <td>
                <a href="#ElementdosageInstruction2">dosageInstruction</a>
            </td>
            <td>
                <span class="mro-circle required" title="Required"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- substitution -->
        <tr>
            <td>
                <a href="#Elementsubstitution2">substitution</a>
            </td>
            <td>
                <span class="mro-circle required" title="Required"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- detectedIssue -->
        <tr>
            <td>
                <a href="#ElementdetectedIssue2">detectedIssue</a>
            </td>
            <td>
                <span class="mro-circle avoid" title="Avoid"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- eventHistory -->
        <tr>
            <td>
                <a href="#ElementeventHistory2">eventHistory</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- id -->
        <tr>
            <td>
                <a href="#Elementid2">id</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- text -->
        <tr>
            <td>
                <a href="#Elementtext4">text</a>
            </td>
            <td>
                <span class="mro-circle optional" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
    </tbody>
</table>

---