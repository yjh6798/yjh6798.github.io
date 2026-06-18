---
layout: page
permalink: /publications/
title: Publications
nav: true
nav_order: 4
---

<style>
.publications {
  counter-reset: pubnum;
}

.publications ol.bibliography {
  padding-left: 0 !important;
  margin-left: 0 !important;
}

.publications ol.bibliography > li {
  counter-increment: pubnum;
  list-style: none !important;
  position: relative;
  padding-left: 3.2rem !important;
  margin-bottom: 1.6rem;
}

.publications ol.bibliography > li::before {
  content: "[" counter(pubnum) "]";
  position: absolute;
  left: 0;
  top: 0;
  font-weight: 600;
  color: #333;
}

.publications h2 {
  color: #333 !important;
  font-weight: 600 !important;
  border-bottom: 1px solid #d8d8d8;
  padding-bottom: 0.35rem;
  margin-top: 2rem;
  margin-bottom: 1.2rem;
  text-align: left !important;
}

.publications .row {
  margin-left: 0 !important;
}

.publications [class*="col-sm"] {
  padding-left: 0 !important;
}
</style>

<div style="margin-bottom: 1.4rem; font-size: 0.92rem; color: #555;">
<strong>†</strong> Equal contribution &nbsp;&nbsp;&nbsp;
<strong>*</strong> Corresponding author
</div>

<div class="publications">

{% bibliography %}

</div>
