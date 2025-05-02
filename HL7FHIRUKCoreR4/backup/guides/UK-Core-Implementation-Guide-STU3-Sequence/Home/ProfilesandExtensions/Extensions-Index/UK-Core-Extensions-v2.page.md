---
topic: Library-Extensions-UKCore
---
## UK Core Extensions

<p>The Extensions listed below have been defined as UK Core extensions. Also included in this library are some HL7 core-defined extensions which have been added to the UK Core profiles because they have been deemed to be "core" to UK FHIR data exchanges. These will have a page with guidance on usage in the UK and examples to illustrate usage.</p>

<p>Note: implementers of UK Core MAY use any HL7 core-defined extension from the HL7 standard regardless of whether the extension is included in this implementation guide. The list of core-defined extensions in FHIR R4 is available in the <a href="http://hl7.org/fhir/R4/extensibility-registry.html" class="external">HL7 Core-defined Extension Registry</a>.</p>

<p>Implementers of the UK Core profiles MAY also create their own Extensions where required, but are encouraged to engage with the UK Core development process to ensure that there is not an existing suitable extension available, and to assist in  guidance around the use of an extension with the UK Core, and with wider use by the UK FHIR Community.</p>



<fql>
from
	StructureDefinition
where
	type = 'Extension' and status != 'retired'
select
	Identity: id, Status: status, Kind:kind, Context: context.expression
</fql>

<script>
$(document).ready(function () {
    const queryString = window.location.search || "?version=current";

    // Convert {{guide-title}} into a URL-safe string
    const guideTitleUrl = "{{guide-title}}"
        .replace(/[^a-zA-Z0-9 ]/g, "")   // remove special characters
        .replace(/\s+/g, "-");           // convert spaces to hyphens

    const baseUrl = `https://simplifier.net/guide/${guideTitleUrl}/`;
    const extensionBase = `${baseUrl}home/profilesandextensions/extensionlibrary/`;
    const profileBase = `${baseUrl}Home/ProfilesandExtensions/UKCore-`;

    // Select your specific table — modify selector if needed
    const $table = $("table.table-bordered");
    if ($table.length === 0) return;

    $table.find("tbody tr").each(function () {
        const $cells = $(this).find("td");
        if ($cells.length < 2) return;

        const $extensionCell = $cells.eq(0);
        const $profilesCell = $cells.eq(3);

        // --- Extension Column ---
        const extText = $extensionCell.text().trim();
        if (extText) {
            const extHref = `${extensionBase}${extText}.page.md${queryString}`;
            $extensionCell.html(`<a href="${extHref}" target="_blank">${extText}</a>`);
        }

        // --- Profiles Column (ignore "Coding", no deduplication) ---
        const profilesRaw = $profilesCell.text().trim().split(";");
        const profileLinks = profilesRaw.map(profile => {
            const clean = profile.trim();
            if (!clean) return "";

            if (clean === "Coding") return "Coding"; // leave as plain text

            const resource = clean.split(".")[0];
            const profileHref = `${profileBase}${resource}${queryString}`;
            return `<a href="${profileHref}" target="_blank">${clean}</a>`;
        }).filter(link => link); // remove any empty ones

        $profilesCell.html(profileLinks.join("<br>"));
    });
});
</script>

