## {{page-title}}

<table id="assets">
<tr>
<th width="50%">Issue</th>
<th width="50%">Proposal</th>
</tr>

<tr>
<td>The Condition.verificationStatus element was constrained out of the Care Connect Condition profile.</td>
<td>During Sprint 4 Clinical and Technical Assurance calls, it was agreed that the UK Core should support the Condition.verificationStatus element.</td>
</tr>

</table>

</br>

<b>Detail:</b>

<ul>
<li>Strong guidance will be issued to highlight that there is the potential for clinical risk associated with some of the values in the FHIR Standard required ConditionVerificationStatus ValueSet associated with this element (Unconfirmed | Provisional | Differential | Confirmed | Refuted | Entered in Error |), and that any risk associated with using this element lies with the sender, and that unless the receiver can support all of these values the sender must not use this element.</li>
<li>Guidance will also be issued in the scenario where if an implementation is not mature enough to send this element but do receive it from other places then it is suggested that the receiver degrades to text any instances other than where the value is "confirmed".</li>
</ul>
