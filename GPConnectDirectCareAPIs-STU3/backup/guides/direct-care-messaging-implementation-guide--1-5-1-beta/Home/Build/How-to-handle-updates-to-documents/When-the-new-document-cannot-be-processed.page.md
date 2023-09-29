## {{page-title}}

- the receiver of the new document **SHOULD** mark the original and replacement as null and void
- an error **SHOULD** be reported to the sender using the ITK response message and appropriate code - see [ITK3 response codes](https://developer.nhs.uk/apis/itk3messagedistribution/explore_response_codes.html) for more information
- the sender of the new document **SHOULD** mark the original and replacement document as null and void if it receives an ITK3 response indicating that the replacement could not be processed