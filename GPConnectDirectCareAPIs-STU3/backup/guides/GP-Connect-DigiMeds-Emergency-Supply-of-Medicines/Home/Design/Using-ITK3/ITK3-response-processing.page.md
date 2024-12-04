## {{page-title}}

Where the message sender requests an ITK3 acknowledgement (known as ITK3 Response), the sending system is responsible for processing the received acknowledgement and acting accordingly.

For example, where an ITK3 Response indicates that a technical error was processed by the receiver when validating the message, the message sender is responsible for taking the action necessary to re-send a corrected message.

More information on the response codes can be found in the article below:

- [Pragmatic use of ITK3 response codes for generic FHIR receive programmes](https://digital.nhs.uk/services/interoperability-toolkit/developer-resources/itk-test-centre/pragmatic-use-of-itk3-response-codes-for-generic-fhir-receive-programmes)