---
layout: page
permalink: /publications/
title: Publications
nav: true
nav_order: 4
---

<style>
.publications {
  max-width: none;
}

/* Publication note */
.publication-note {
  margin: 0 0 1.2rem 0;
  font-size: 0.92rem;
  color: var(--global-text-color-light);
}

/* Year headings */
.publications h2 {
  color: var(--global-text-color) !important;
  font-size: 1.85rem !important;
  font-weight: 600 !important;
  line-height: 1.25 !important;
  text-align: left !important;
  border-top: 1px solid var(--global-divider-color) !important;
  border-bottom: 1px solid var(--global-divider-color) !important;
  padding: 1rem 0 0.35rem 0 !important;
  margin: -0.35rem 0 1.5rem 0 !important;
}

/* Bibliography layout */
.publications ol.bibliography {
  width: 100% !important;
  padding-left: 0 !important;
  margin-left: 0 !important;
  visibility: hidden;
}

.publications.pub-loaded ol.bibliography {
  visibility: visible;
}

.publications ol.bibliography > li {
  list-style: none !important;
  display: flex !important;
  align-items: flex-start !important;
  gap: 0.8rem !important;
  margin-bottom: 2rem !important;
  padding-left: 0 !important;
  max-width: 100% !important;
  min-width: 0 !important;
}

/* Publication numbering */
.publications ol.bibliography > li::before {
  content: attr(data-pubnum) ".";
  flex: 0 0 28px;
  width: 28px;
  text-align: right;
  font-size: 1.05rem;
  font-weight: 500;
  line-height: 1.45;
  color: var(--global-text-color);
}

/* Publication row */
.publications ol.bibliography > li > .row {
  flex: 1 1 auto !important;
  width: 100% !important;
  min-width: 0 !important;
  margin: 0 !important;
}

.publications ol.bibliography > li > .row > [class*="col-"] {
  flex: 0 0 100% !important;
  max-width: 100% !important;
  min-width: 0 !important;
  padding: 0 !important;
  margin: 0 !important;
}

/* Publication titles */
.publications ol.bibliography .title {
  display: block !important;
  margin: 0 0 0.08rem 0 !important;
  padding: 0 !important;
  line-height: 1.45 !important;
  font-weight: 600 !important;
  color: var(--global-text-color) !important;
  overflow-wrap: anywhere;
}

/* Authors */
.publications ol.bibliography .author,
.publications ol.bibliography .authors {
  display: block !important;
  line-height: 1.45 !important;
  color: var(--global-text-color) !important;
  overflow-wrap: anywhere;
}

/* Highlight my name */
.publications .my-name {
  color: var(--global-theme-color) !important;
  font-weight: 400 !important;
}

/* Journal names and publication details */
.publications ol.bibliography .periodical {
  display: block !important;
  margin: 0.15rem 0 0 0 !important;
  line-height: 1.35 !important;
  color: var(--global-text-color) !important;
  overflow-wrap: anywhere;
}

.publications ol.bibliography .periodical em,
.publications ol.bibliography .periodical i {
  font-style: italic !important;
}

/* Additional publication information */
.publications ol.bibliography .note,
.publications ol.bibliography .status,
.publications ol.bibliography .year {
  color: var(--global-text-color-light) !important;
}

/* Hide unnecessary bibliography elements */
.publications ol.bibliography .abbr,
.publications ol.bibliography .abstract,
.publications ol.bibliography .award,
.publications ol.bibliography .bibtex,
.publications ol.bibliography .hidden {
  display: none !important;
}

/* Publication links */
.publications ol.bibliography .links {
  display: block !important;
  margin-top: 0.38rem !important;
}

/* DOI and other buttons */
.publications ol.bibliography .links .btn {
  padding: 0.08rem 0.42rem !important;
  font-size: 0.62rem !important;
  line-height: 1.15 !important;
  font-weight: 500 !important;
  border: 1px solid var(--global-text-color-light) !important;
  border-radius: 2px !important;
  color: var(--global-text-color) !important;
  background: transparent !important;
  box-shadow: none !important;
  text-transform: uppercase !important;
  letter-spacing: 0.02em !important;
}

/* Button hover */
.publications ol.bibliography .links .btn:hover {
  color: var(--global-bg-color) !important;
  border-color: var(--global-text-color) !important;
  background: var(--global-text-color) !important;
  text-decoration: none !important;
}

/* Mobile layout */
@media (max-width: 768px) {
  .publications ol.bibliography > li {
    gap: 0.65rem !important;
  }

  .publications ol.bibliography > li::before {
    flex-basis: 24px;
    width: 24px;
    font-size: 1rem;
  }
}
</style>

<div class="publication-note">
<strong>†</strong> Equal contribution
&nbsp;&nbsp;&nbsp;
<strong>*</strong> Corresponding author
</div>

<div class="publications">

{% bibliography %}

</div>

<script>
(function () {
  function cleanPublications() {
    const pub = document.querySelector(".publications");
    if (!pub) return;

    const lists = Array.from(pub.querySelectorAll("ol.bibliography"));

    lists.forEach(function (list) {
      list.innerHTML = list.innerHTML
        .replace(/,\s*(19|20)\d{2}(?=\s*(<|$|\.|,))/g, "")
        .replace(/\s*\(\s*(19|20)\d{2}\s*\)/g, "")
        .replace(/>\s*,\s*(19|20)\d{2}\s*</g, "><")
        .replace(/>\s*,\s*(19|20)\d{2}/g, ">")
        .replace(/\s+(19|20)\d{2}(?=\s*<)/g, "")
        .replace(/,\s*,/g, ",")
        .replace(/,\s*\./g, ".")
        .replace(/,\s*</g, "<")
        .replace(/\s{2,}/g, " ");
    });

    pub.querySelectorAll(".author, .authors").forEach(function (block) {
      block.innerHTML = block.innerHTML.replace(
        /Jounghyun Yoo([†*])?/g,
        '<span class="my-name">Jounghyun Yoo$1</span>'
      );
    });

    pub.querySelectorAll(".periodical").forEach(function (periodical) {
      const rawText = periodical.textContent.trim();

      if (!rawText || /under revision|in press|featured|cover/i.test(rawText)) {
        return;
      }

      const parts = rawText.split(",");
      if (parts.length < 2) return;

      const journal = parts.shift().trim();
      const details = parts.join(",").trim();

      if (!journal || !details) return;

      periodical.innerHTML = "<em>" + journal + "</em>, " + details;
    });

    /* Final numbering across all years */
    const allItems = Array.from(pub.querySelectorAll("ol.bibliography li"));
    let number = allItems.length;

    allItems.forEach(function (item) {
      item.setAttribute("data-pubnum", number);
      number -= 1;
    });

    pub.classList.add("pub-loaded");
  }

  if (document.readyState === "loading") {
    document.addEventListener("DOMContentLoaded", cleanPublications);
  } else {
    cleanPublications();
  }
})();
</script>
