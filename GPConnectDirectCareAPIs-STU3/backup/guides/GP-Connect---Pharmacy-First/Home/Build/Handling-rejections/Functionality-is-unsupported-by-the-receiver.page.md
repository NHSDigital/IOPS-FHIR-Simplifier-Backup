## {{page-title}}

There are two scenarios in where NHS GP IT suppliers may need to send an ITK3 `20010` rejection code.

**1: GP Practice has "toggled-off" Update Record messages**

NHS GP IT suppliers provide the functionality for individual GP practices to toggle-off Update Record.


**2: NHS GP IT supplier doesn't currently support Update Record messages**

It is possible that some GP Practies are using NHS GP IT software which may not have built the functionality to support Update Record.

In such scenarios this specification requests that NHS IT suppliers send an ITK3 `20010` code.

ITK3 states that `20010` should be used when:

> The Recipient Organisation identified in the Payload, is not supported by this End Point (Receiving System).

For the purpose of Update Record, this code will indicate to the sender that the receiving system is not configured to receive the payload.

If a sending system receives this code, then the sending system must send information about the consultation as a PDF via an alternative method, such as e-mail, to the GP practice, so it can be manually uploaded to the GP patient record.

---