## {{page-title}}

<div class="nhsd-a-box nhsd-a-box--bg-light-yellow nhsd-!t-margin-bottom-6 nhsd-t-body">
    <b>Important</b>: The entire ITK3 message will be rejected if unsupported profiles are sent.
</div>

This is because ITK3 does not lend itself to chatty acknowledgements to articulate to the sending system that only part of the information has been accepted and the rest has rejected.

This could introduce <b>clinical risk</b>.

<div class="nhsd-a-box nhsd-a-box--bg-light-blue nhsd-!t-margin-bottom-6 nhsd-t-body">
    It is safer for the receiver to reject the entire message, with the ITK3 rejection code: <code>20009</code> (Payload content validation has failed).
</div>


[ITK3 Response Codes (2.10.0-live)](https://developer.nhs.uk/apis/itk3messagedistribution-2-10-0/explore_response_codes.html)


---