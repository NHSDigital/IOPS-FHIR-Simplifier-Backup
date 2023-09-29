## {{page-title}}

### Is there an agreed list of Document types to use? 

Yes, the Professional Record Standards Body (PRSB) have set the [recommended standards](https://www.digihealthcare.scot/app/uploads/2022/07/CDI-Standard-v4-1-FINAL.pdf?hsCtaTracking=b259f952-5cd2-4ce4-9648-9e572241bf4c%7C181effb1-bd74-414c-8841-47070199739d).  

However, as these standards are not yet used in GP systems, historic files may not adhere to the standards. Additionally, GP practices have their own list of Document types and may not be standardised (which may also include free text). 

GP Connect recommends the use of the ‘Record composition type simple reference set (foundation metadata concept)’ with SNOMED codes from the Refset Id 1127551000000109. A text value can be provided for values that do not exist in the valueset. 

JSON file type examples: found in the contentType tags (These are not all the items that can be sent): 

- image/jpeg 

- image/png 

- image/tiff 

- image/bmp 

- application/msword 

- application/pdf 

- application/xml 

- text/plain 

- text/richtext 

- video/mpeg 

- audio/x-au 

### Are local Document formats accepted? 

Documents of industry standard formats are allowed. Any local Document formats are not allowed. Local Documents are considered bespoke software that generate an uncommon mime type that may not be recognised (it can't be guaranteed that other applications can support this when opened). Metadata can be made available but not the binary file. 

### What if a Document is in a non-standard format?

It is possible for a Consumer to mark this or make this visible. 

### How is best practice defined in the case of multiple Document versions? 

Providers shall only return latest version of the Document via the GP Connect APIs. 

### How are clinical Documents version identified? 

Versioning is not specified. Inspection of the file is needed to determine the version. (Only applicable if the data is being called multiple times).