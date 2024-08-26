## {{page-title}}

The consuming system **MUST** provide role based access controls to the HTML section retrieval at an appropriate level such that the consuming organisation can meet its obligations as described in the Information governance principles page.

Please refer to the consumer support page, Developing a restricted Access Record: HTML view, for additional guidance.

The consuming organisation **MUST** provide appropriate support to its users to understand the error messages associated with the HTML sections as follows.

### Error handling

If a GP principal system can’t meaningfully supply content for a requested HTML section (or subset of the Summary View) then the system **MUST** return the following HTML fragment in place of the HTML table.

#### Supported but hasn’t been recorded

*   system can store the data
*   BUT no data has been recorded for the patient

```
<div>
	<p>No '[section]' data is recorded for this patient.</p>
</div>
```
#### Supported but can’t be technically provided

*   system can store the data
*   BUT no data is available for the patient via the GP Connect APIs due to a technical limitation

```
<div>
	<p>This system does not support retrieval of '[section]' data.</p>
	<p>This data may still exist in the source system.</p>
</div>
```

#### Supported but is masked/access denied

*   system can store the data
*   BUT no data is available for the patient via the GP Connect APIs due to an IG/DS rule

```
<div>
	<p>Access is denied to '[section]' data for this patient.</p>
	<p>This data may still exist in the source system.</p>
</div>
```

#### Not supported

*   system doesn’t store the data

```
<div>
	<p>'[section]' data is not supported by this system.</p>
</div>
```