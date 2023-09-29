## {{page-title}}

Where the message sender requests an ITK3 acknowledgement (known as ITK3 Response), the sending system is responsible for processing the received acknowledgement and acting accordingly.

For example, where an ITK3 Response indicates that a technical error was processed by the receiver when validating the message, the message sender is responsible for taking the action necessary to re-send a corrected message.

Please refer to the [messaging capability](https://simplifier.net/guide/gp-connect--update-record--itk3/Home/Design/Design-overview?version=current#Using-messaging-to-perform-updates) and [messaging use case pages](https://simplifier.net/guide/gp-connect--update-record--itk3/Home/Design/Design-overview?version=current#Who-will-be-interested-in-this-capability) for details of which of these options is mandated or recommended for the message being created.

