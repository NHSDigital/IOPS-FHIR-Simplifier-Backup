## {{page-title}}

### Read Code
All Read Codes should be represented using a full five characters.
- Where 4-byte codes are used these must be preceded by a full-stop as in the NHS Clinical Terms superset (e.g. 4-byte code "6521" is represented as ".6521").
- Trailing full-stops are significant and must be included (e.g. "H43" is not a valid Read Code and must be represented in full as "H43..").
    - Care should be taken in any environment where a Read Code may have been subjected to auto-correction because:
        - Upper/lower case is significant
        - Conversion of a sequence of three full-stops "..." to a single "…" (ASCII Hex "85" Unicode Hex "2026") special character occurs in some environments and creates invalid Read Codes.

### Read Code version 2 term code
Read Codes Version 2 uses a "Term Code" to distinguish between some alternative terms associated with the same Read Code. A Term Code is represented as a two digit string and is only unique within the context of a single Read Code.

It is now widely recognised that many of the terms associated with a Read Code are not true synonyms. This issue was partially resolved in NHS Clinical Terms Version 3 and further disambiguation has occurred in development of SNOMED Clinical Terms. However, in the meantime where Term Codes are stored these should be communicated with the Read Code.

A Read Code + Term Code combination is communicated as a single seven character code. Thus the code "7001200" represents the Term Code "00" associated with the Read Code "70012".

Note that this specification requires the term to be conveyed in the message in addition to any coded representation. Therefore, safe communication is not dependent on use of the Term Code in all systems. Therefore, a sending system that does not support Term Codes for a particular item of information should not send a Term Code. Similarly a receiving system that does not support Term Code storage may ignore the Term Code when constructing a record entry. However, where a sending system stores the Term Code this should be included in the message and where a receiving system stores the Term Code this should be retrieved from the message.

### NHS Clinical Terms Version 3 – Term Id
In NHS Clinical Terms Version 3 the TermId is a five character string that uniquely identifies an associated term (or set of two or three terms of alternative lengths). Although it is globally unique it says nothing about the associated concept and thus must be combined with the Read Code. There are no plans to use the TermID in NHS Clinical Terms Version 3 and thus inclusion of TermId is not permitted. 