## Hyperlinks 

|Markdown|Usage
|-
|\[link title]\(link) |External Links. Only to be used to link to pages within https://hl7.org/fhir/ and https://simplifier.net/ 
|\<a href="link" class="external">link title\</a> |External Links. Only to be used to link to pages that are not on https://hl7.org/fhir/ and https://simplifier.net/ 
|\{ \{pagelink:yaml-topic\}\}|Internal Link. For referencing within the IG.  

**Note:** External links SHALL have class="external" set.

**Note:** The Topic url can be found using the dropdown button within the IG editor, or for pages named 'Index' these are manually created and can be found at the top of the page. See {{pagelink:YAML-Headers}} for more details.

**Note:** When linking to an Asset on a different Simplifier IG, the link SHALL only include a `?version=` url parameter if a specific published version is to be targetted. By not includeing a `?version=` url parameter, the link will automatically target the default (published or current) version.


---