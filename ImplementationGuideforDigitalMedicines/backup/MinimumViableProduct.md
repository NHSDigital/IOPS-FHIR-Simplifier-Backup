## Minimum Viable Product

Links to the definitions of `MedicationRequest` covered within this guidance:

- [R4 Resource](https://www.hl7.org/fhir/medicationrequest.html)
- [UK Core Resource](https://simplifier.net/ukcore-v2/ukcoremedicationrequest)

<table data-responsive>
    <thead>
        <tr>
            <th>Element</th>
            <th data-no-sort>MVP</th>
            <th data-no-sort>R4</th>
            <th data-no-sort>UK Core</th>
            <th data-no-sort>GP Connect (STU3)</th>
        </tr>
    </thead>
    <tbody>
        <!-- identifier -->
        <tr>
            <td>
                <a href="#Elementidentifier">identifier</a>
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
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- status -->
        <tr>
            <td>
                <a href="#Elementstatus">status</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- statusReason -->
        <tr>
            <td>
                <a href="#ElementstatusReason">statusReason</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- intent -->
        <tr>
            <td>
                <a href="#Elementintent">intent</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- category -->
        <tr>
            <td>
                <a href="#Elementcategory">category</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- priority -->
        <tr>
            <td>
                <a href="#Elementpriority">priority</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- doNotPerform -->
        <tr>
            <td>
                <a href="#ElementdoNotPerform">doNotPerform</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- reported[x] -->
        <tr>
            <td>
                <a href="#Elementreporetedx">reported[x]</a>
            </td>
            <td>
                <span class="mro-circle unknown" title="Unknown"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
            <td>
                <i class="fas fa-times text-danger"</i>            
            </td>
        </tr>
        <!-- medication[x] -->
        <tr>
            <td>
                <a href="#Elementmedicationx">medication[x]</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- subject -->
        <tr>
            <td>
                <a href="#Elementsubject">subject</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- encounter -->
        <tr>
            <td>
                <a href="#Elementencounter">encounter</a>
            </td>
            <td>
                <span class="mro-circle unknown" title="Unknown"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- supportingInformation -->
        <tr>
            <td>
                <a href="#ElementsupportingInformation">supportingInformation</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- authoredOn -->
        <tr>
            <td>
                <a href="#ElementauthoredOn">authoredOn</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- requester -->
        <tr>
            <td>
                <a href="#Elementrequester">requester</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- performer -->
        <tr>
            <td>
                <a href="#Elementperformer3">performer</a>
            </td>
            <td>
                <span class="mro-circle unknown" title="Unknown"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- performerType -->
        <tr>
            <td>
                <a href="#ElementperformerType">performerType</a>
            </td>
            <td>
                <span class="mro-circle unknown" title="Unknown"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- recorder -->
        <tr>
            <td>
                <a href="#Elementrecorder">recorder</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- reasonCode -->
        <tr>
            <td>
                <a href="#ElementreasonCode">reasonCode</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- reasonReference -->
        <tr>
            <td>
                <a href="#ElementreasonReference">reasonReference</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- instantiatesCanonical -->
        <tr>
            <td>
                <a href="#ElementinstantiatesCanonical">instantiatesCanonical</a>
            </td>
            <td>
                <span class="mro-circle unknown" title="Unknown"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- instantiatesUri -->
        <tr>
            <td>
                <a href="#ElementinstantiatesUri">instantiatesUri</a>
            </td>
            <td>
                <span class="mro-circle unknown" title="Unknown"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- basedOn -->
        <tr>
            <td>
                <a href="#ElementbasedOn2">basedOn</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- groupIdentifier -->
        <tr>
            <td>
                <a href="#ElementgroupIdentifier">groupIdentifier</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- courseOfTherapyType -->
        <tr>
            <td>
                <a href="#ElementcourseOfTherapyType">courseOfTherapyType</a>
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
            <td>
                <i class="fas fa-times text-danger"</i>            
            </td>
        </tr>
        <!-- insurance -->
        <tr>
            <td>
                <a href="#Elementinsurance">insurance</a>
            </td>
            <td>
                <span class="mro-circle unknown" title="Unknown"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
            <td>
                <i class="fas fa-times text-danger"</i>            
            </td>
        </tr>
        <!-- note -->
        <tr>
            <td>
                <a href="#Elementnote">note</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- dosageInstruction -->
        <tr>
            <td>
                <a href="#ElementdosageInstruction">dosageInstruction</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- dispenseRequest -->
        <tr>
            <td>
                <a href="#ElementdispenseRequest">dispenseRequest</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- substitution -->
        <tr>
            <td>
                <a href="#Elementsubstitution">substitution</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- priorPrescription -->
        <tr>
            <td>
                <a href="#ElementpriorPrescription">priorPrescription</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- detectedIssue -->
        <tr>
            <td>
                <a href="#ElementdetectedIssue">detectedIssue</a>
            </td>
            <td>
                <span class="mro-circle avoid" title="Optional"></span>
            </td>
            <td>
                <i class="fas fa-check text-success"></i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
        <!-- eventHistory -->
        <tr>
            <td>
                <a href="#ElementeventHistory">eventHistory</a>
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
            <td>
                <i class="fas fa-check text-success"</i>
            </td>
        </tr>
        <!-- text -->
        <tr>
            <td>
                <a href="#Elementtext">text</a>
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
            <td>
                <i class="fas fa-check text-success"</i>            
            </td>
        </tr>
    </tbody>
</table>

---