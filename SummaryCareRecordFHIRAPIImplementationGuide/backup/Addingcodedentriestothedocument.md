## Adding coded entries to the document

Coded entries are added to the Composition by referencing the coded entry from the relavant section within the document.

For example, a Composition may have a section for Investigation Results that has two COVID coded entries.

In this case, the Composition is constructed using sections (as per a Composition not using coded entries). Note that text section of the Composition should always carry all of the Summary Care Record. The coded entries are inserted into the section as references (in Composition.section.entry) to the relevent resource that is carried within the Bundle, but outside the Composition as follows:

```xml
<Bundle>
    <!--Bundle bits go here-->
    <Composition>
        <!--Compostion header bits - subject, author etc. go here-->
        <section>
            <title value="Investigation Results"/>
			<!--All information must be in text-->
            <text>
            	<table id="Results">
					<thead>
						<tr>
						<th>Date</th>
						<th>Description</th>
						<th>Value</th>
						<th>Supporting Information</th>
						</tr>
					</thead>
 					<tbody>
						<tr class="oddRow">
						<td>05 August 2020</td>
						<td>Severe acute respiratory syndrome coronavirus 2 immunity status (observable entity)</td>
						<td/>
						<td/>
						</tr>
    					<tr class="evenRow">
						<td>05 August 2020</td>
						<td>Severe acute respiratory syndrome coronavirus 2 immunoglobulin G detected (finding)</td>
						<td/>
						<td/>
						</tr>
                    </tbody>
                </table>
            </text>
			<!--coded entries are referenced from the entry within the Bundle-->
            <entry>
                <reference  value="urn:uuid:09c5531f-e0e2-43bf-9efb-16f4d2ac2221"/>
            </entry>
            <entry>
                <reference value="urn:uuid:49eecb91-b602-42bd-be1d-03a434193f59"/>
            </entry>
        </section>
        <!--there may be more sections -->
    </Composition>
    <!--coded entry 1-->
	<entry>
		<fullUrl value="urn:uuid:09c5531f-e0e2-43bf-9efb-16f4d2ac2221"/>
		<resource>
   			<Observation>
        		<id value="09c5531f-e0e2-43bf-9efb-16f4d2ac2221"/>
        		<meta>
            		<profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation" />
        		</meta>
        		<status value="final"/>
        		<code>
            		<coding>
                		<system value="http://snomed.info/sct"/>
		                <code value="1321361000000102"/>
        		        <display value="Severe acute respiratory syndrome coronavirus 2 immunity status (observable entity)"/>
            		</coding>
        		</code>
        		<effectiveDateTime value="2020-08-05"/>
    		</Observation>
		</resource>
	</entry>
	<!--coded entry 2-->
		<entry>
			<fullUrl value="urn:uuid:49eecb91-b602-42bd-be1d-03a434193f59"/>
			<resource>
    			<Observation>
        			<id value="49eecb91-b602-42bd-be1d-03a434193f59"/>
        			<meta>
            			<profile value="https://fhir.hl7.org.uk/StructureDefinition/UKCore-Observation" />
        			</meta>
        			<status value="final"/>
        			<code>
            			<coding>
                			<system value="http://snomed.info/sct"/>
                			<code value="1321541000000108"/>
			                <display value="Severe acute respiratory syndrome coronavirus 2 immunoglobulin G detected (finding)"/>
            			</coding>
        			</code>
        			<effectiveDateTime value="2020-08-05"/>
    			</Observation>
		</resource>
	</entry>
</Bundle>
```