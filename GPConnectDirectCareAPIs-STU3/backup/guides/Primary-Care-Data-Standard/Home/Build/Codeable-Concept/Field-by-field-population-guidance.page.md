## {{page-title}}
<table>
    <thead>
        <tr>
            <th>Level</th>
            <th>Field</th>
            <th>Directions</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1 </td>
            <td>coding (SNOMED CT) </td>
            <td>Populate this group if a SNOMED CT concept id is stored for the item.</td>
        </tr>
        <tr>
            <td>2</td>
            <td>system</td>
            <td>Set to “http://snomed.info/sct”.</td>
        </tr>
        <tr>
            <td>2</td>
            <td>code</td>
            <td>The SNOMED CT concept id stored for the item.</td>
        </tr>
        <tr>
            <td>2</td>
            <td>display</td>
            <td>The text of the current preferred term of the SNOMED CT concept
            id according to the current NHS Realm Language Reference Sets.
            The text of the preferred term of the SNOMED CT concept id.
            The preferred term is the description specified for the concept in
            the NHS realm description subset. The preferred term for a
            concept may change over time. The sending system should
            determine the current preferred term for the concept.</td>
        </tr>
        <tr>
            <td>2</td>
            <td>descriptionId</td>
            <td>The SNOMED CT descriptionId recorded with the item. Only
            populated if a descriptionId exists.</td>
        </tr>
        <tr>
            <td>2</td>
            <td>descriptionDisplay</td>
            <td>The text of the description id. Only populated if a descriptionId
            exists and there is no need to populate this field if the text
            is lexically identical to the text in coding.display .</td>
        </tr>
        <tr>
            <td>2</td>
            <td>userSelected</td>
            <td>Set to TRUE if a user selected the SNOMED Code when
            creating/updating this item. If this is FALSE then this element
            MUST not be populated by the supplying system.
            For consuming systems the absence of this element therefore
            indicates that it is FALSE.</td>
        </tr>
        <tr>
            <td>1 </td>
            <td>coding (other) </td>
            <td>Populate this group if a clinical code other than SNOMED CT is
            stored for the item. If there are multiple codes (that is,. the item
            has been translated multiple times) there is a group entry per
            code.</td>
        </tr>
        <tr>
            <td>2</td>
            <td>system</td>
            <td>The identification of the code system that defines the meaning
            of the symbol in the code.</td>
        </tr>
        <tr>
            <td>2</td>
            <td>code</td>
            <td>The clinical code associated with the item.</td>
        </tr>
        <tr>
            <td>2</td>
            <td>display</td>
            <td>The longest character length variant text associated with the
            current preferred term for the clinical code.</td>
        </tr>
        <tr>
            <td>2</td>
            <td>descriptionId</td>
            <td>Do not populate (SNOMED CT only).</td>
        </tr>
        <tr>
            <td>2</td>
            <td>descriptionDisplay</td>
            <td>Do not populate (SNOMED CT only).</td>
        </tr>
        <tr>
            <td>2</td>
            <td>userSelected</td>
            <td>Set to TRUE if a user selected this code when
            creating/updating this item. If this is FALSE then this element
            MUST not be populated by the supplying system.
            For consuming systems the absence of this element therefore
            indicates that it is FALSE.</td>
        </tr>
        <tr>
            <td>1 </td>
            <td>text </td>
            <td>The original text selected/manually entered by the user for the item.
            Only populate when there is no user selected translation set with a
            display or descriptionDisplay recorded.
            If the text displayed to the user when they entered the code on the
            system is not lexically identical to the term of the code then the
            displayed text must be populated here.
            <br><b>Note: This occurs when either the original entry was not coded
            or the original coding has been lost.</b></td>
        </tr>
    </tbody>
</table>