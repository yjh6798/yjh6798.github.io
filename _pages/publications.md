---
layout: page
permalink: /publications/
title: Publications
nav: true
nav_order: 4
---

<style>
/* Numbering */
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
  display: flex;
  align-items: flex-start;
  gap: 0.8rem;
  margin-bottom: 2rem;
  padding-left: 0 !important;
}

/* Publication number */
.publications ol.bibliography > li::before {
  content: counter(pubnum) ".";
  flex: 0 0 24px;
  width: 24px;
  text-align: right;
  font-size: 1.05rem;
  font-weight: 500;
  line-height: 1.45;
  padding-top: 0.10rem;
  color: #222;
}

/* Main publication block */
.publications ol.bibliography > li > .row {
  flex: 1;
  margin: 0 !important;
}

.publications ol.bibliography > li > .row > [class*="col-"] {
  flex: 0 0 100% !important;
  max-width: 100% !important;
  padding: 0 !important;
  margin: 0 !important;
}

/* Title */
.publications .title {
  margin-top: 0 !important;
  margin-bottom: 0.15rem !important;
  line-height: 1.45 !important;
  font-weight: 600 !important;
}

/* Authors */
.publications .author,
.publications .authors {
  line-height: 1.45 !important;
}

/* Journal */
.publications .periodical {
  margin-top: 0.15rem !important;
  line-height: 1.35 !important;
}

/* DOI button */
.publications .links {
  margin-top: 0.45rem !important;
}

.publications .links .btn {
  padding: 0.18rem 0.55rem !important;
  font-size: 0.72rem !important;
}

/* Year */
.publications h2 {
  color: #333 !important;
  font-weight: 600 !important;
  border-bottom: 1px solid #d8d8d8;
  padding-bottom: 0.35rem;
  margin-top: 2rem;
  margin-bottom: 1.2rem;
  text-align: left !important;
}
</style>

<div style="margin-bottom:1.4rem;font-size:0.92rem;color:#555;">
<strong>†</strong> Equal contribution
&nbsp;&nbsp;&nbsp;
<strong>*</strong> Corresponding author
</div>

<div class="publications">

{% bibliography %}

</div>
