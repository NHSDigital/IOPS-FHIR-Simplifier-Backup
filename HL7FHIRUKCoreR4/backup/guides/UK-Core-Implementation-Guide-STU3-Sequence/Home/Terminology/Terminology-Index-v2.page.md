---
topic: Library-ValueSetsAndCodeSystems
---
## Terminology

---



## ValueSets and CodeSystems

This is the list of ValueSets and CodeSystems defined for use within the UK Core. 

Other ValueSets are usable if the binding strength is defined as extensible. For more information see
[HL7 FHIR - Binding Strengths](http://hl7.org/fhir/R4/terminologies.html#strength).

<div markdown="span" class="alert alert-warning" role="alert"><h4><i class="fa fa-warning"></i> Important note regarding ValueSet expansions:</h4>
Within this release of the UK Core, ValueSet expansions have been incorporated into the ValueSets. For some ValueSets containing SNOMED CT or dm+d data in particular, the number of concepts were deemed too large to expand. It should also be remembered that the expansions of SNOMED CT data in particular represent the content available at the time the expansion was generated, but that this content can subsequently change. For an up to date and complete list of values, suppliers SHOULD consult the latest SNOMED CT terminology release.
</div>

<style>
 [class*=override] {
 	background-color:#f2f2f2;
	 }
</style>

<fql>
from
	ValueSet
select
	ValueSet: id, Status: status, CodeSystem: compose.include.system, ValueSets: compose.include.valueSet
order by
	id
distinct
</fql>

<script>
document.addEventListener("DOMContentLoaded", function () {
  // Locate the table
  const table = document.querySelector("table.table-bordered");
  if (!table) return;

  // Change header
  const headerRow = table.querySelector("thead tr");
  if (headerRow && headerRow.children.length >= 4) {
    headerRow.children[2].innerText = "Composed of";
    headerRow.removeChild(headerRow.children[3]);
  }

  // Combine the two columns in each row
  const rows = table.querySelectorAll("tbody tr");
  rows.forEach(row => {
    const cells = row.children;
    if (cells.length >= 4) {
      const composed = new Set();

      // Extract systems (split by ';' if needed)
      cells[2].innerText.split(";").forEach(item => composed.add(item.trim()));
      // Extract valueSets
      cells[3].innerText.split(";").forEach(item => composed.add(item.trim()));

      // Remove duplicates and join with line breaks
      const combined = Array.from(composed).filter(v => v).join("<br>");
      cells[2].innerHTML = combined;

      // Remove the 4th column (original valueSets)
      row.removeChild(cells[3]);
    }
  });
});
</script>

<!-- JQuery to seperate CodeSystems onto seperate lines per ValueSet and remove dulicate CodeSystems-->

<script>
$(document).ready(function () {
    const fullUrl = window.location.href;
    const guideBase = fullUrl.split("/home/")[0] + "/home/";
    const queryString = window.location.search || "";

    const $table = $("table.table-bordered");
    if ($table.length === 0) return;

    // Update header
    const $headerCells = $table.find("thead tr th");
    if ($headerCells.length >= 4) {
        $headerCells.eq(2).text("Composed of");
        $headerCells.eq(3).remove(); // remove old 4th column
    }

    // Process each row
    $table.find("tbody tr").each(function () {
        const $cells = $(this).find("td");
        if ($cells.length < 4) return;

        const $nameTd = $cells.eq(0);
        const $statusTd = $cells.eq(1);
        const $systemTd = $cells.eq(2);
        const $valueSetTd = $cells.eq(3);

        // --- Update name column to link to ValueSet page ---
        const nameValue = $nameTd.text().trim();
        if (nameValue.startsWith("UKCore")) {
            const assetLower = nameValue.toLowerCase();
            const href = `${guideBase}terminology/valuesets/valueset-${assetLower}.page.md${queryString}`;
            $nameTd.html(`<a href="${href}" target="_blank">${nameValue}</a>`);
        }

        // --- Combine system + valueset URLs ---
        const combinedLinks = [];

        const addLinks = (text) => {
            text.split(";").forEach(item => {
                const trimmed = item.trim();
                if (!trimmed) return;

                let linkHref = trimmed;
                let linkText = trimmed;

                if (trimmed.startsWith("https://fhir.hl7.org.uk/")) {
                    const parts = trimmed.split("/");
                    const assetType = parts[3];
                    const assetName = parts[4];
                    const sectionPath =
                        assetType.toLowerCase() === "codesystem"
                            ? "terminology/codesystems/codesystem-"
                            : assetType.toLowerCase() === "valueset"
                            ? "terminology/valuesets/valueset-"
                            : null;

                    if (sectionPath && assetName) {
                        const lowerAsset = assetName.toLowerCase();
                        linkHref = `${guideBase}${sectionPath}${lowerAsset}.page.md${queryString}`;
                    }
                }

                combinedLinks.push(`<a href="${linkHref}" target="_blank">${linkText}</a>`);
            });
        };

        addLinks($systemTd.text());
        addLinks($valueSetTd.text());

        // Remove duplicates by text
        const unique = Array.from(new Map(combinedLinks.map(link => [$(link).text(), link])).values());

        $systemTd.html(unique.join("<br>"));
        $valueSetTd.remove(); // Remove now-merged ValueSet column
    });
});
</script>

<!--<script>
$(document).ready(function () {
  $(".table tbody tr").each(function () {
    var $systemCell = $(this).find("td:eq(2)");
    var $links = $systemCell.find("a");

    let seen = new Set();
    let uniqueLinks = [];

    $links.each(function () {
      var href = $(this).attr("href");
      if (!seen.has(href)) {
        seen.add(href);
        uniqueLinks.push($(this).clone());
      }
    });

    if (uniqueLinks.length > 1) {
      $systemCell.empty();
      uniqueLinks.forEach(function ($link, index) {
        if (index > 0) $systemCell.append("<br>");
        $systemCell.append($link);
      });
    }
  });
});

function rewriteFQLTableLinks() {
    const fullUrl = window.location.href;
    const guideBase = fullUrl.split("/home/")[0] + "/home/";
    const queryString = window.location.search || "";

    $("table.table tbody tr").each(function () {
        const $tds = $(this).find("td");
        const $nameTd = $tds.eq(0);
        const $statusTd = $tds.eq(1);
        const $systemTd = $tds.eq(2);

        // --- Update 'name' column to be a link to the ValueSet page ---
        const nameValue = $nameTd.text().trim();
        if (nameValue.startsWith("UKCore")) {
            const assetLower = nameValue.toLowerCase();
            const href = `${guideBase}terminology/valuesets/valueset-${assetLower}.page.md${queryString}`;
            $nameTd.html(`<a href="${href}" target="_blank">${nameValue}</a>`);
        }

        // --- Rewrite 'system' column: remove duplicates, format links, split by <br> ---
        const $links = $systemTd.find("a");
        if ($links.length === 0) return;

        const seen = new Set();
        const newSystemContent = [];

        $links.each(function () {
            const $a = $(this);
            const text = $a.text().trim();
            if (seen.has(text)) return;
            seen.add(text);

            let finalHref = $a.attr("href"); // fallback

            if (text.startsWith("https://fhir.hl7.org.uk/")) {
                const urlParts = text.split("/");
                const assetType = urlParts[3]; // CodeSystem or ValueSet
                const assetName = urlParts[4]; // UKCore-...

                if (assetType && assetName) {
                    const sectionPath = (assetType.toLowerCase() === "codesystem")
                        ? "terminology/codesystems/codesystem-"
                        : (assetType.toLowerCase() === "valueset")
                            ? "terminology/valuesets/valueset-"
                            : null;

                    if (sectionPath) {
                        const lowerAsset = assetName.toLowerCase();
                        finalHref = `${guideBase}${sectionPath}${lowerAsset}.page.md${queryString}`;
                    }
                }
            }

            newSystemContent.push(`<a href="${finalHref}" target="_blank">${text}</a>`);
        });

        $systemTd.html(newSystemContent.join("<br>"));
    });
}

$(document).ready(function () {
    rewriteFQLTableLinks();
});
</script>-->















