## {{page-title}}

Although MESH can handle very large files, it is possible that receiving systems are configured to reject attachments received over a certain size. In the event of this happening, an infrastructure acknowledgement will be returned to the sender:

[20015 – Message Too Large](https://nhsconnect.github.io/ITK3-FHIR-Messaging-Distribution/explore_response_examples.html#infrastructure-level-response-20015-message-too-large)


If the intended recipient is unable to receive this information, we recommended the sender provides additional metadata in the summary PDF regarding the attachments that are unable to be sent - such as the:

- file name
- file timestamp
- file size

This is so that the receiving GP practice can contact the sender of the payload for more information about the attachments, if required.
