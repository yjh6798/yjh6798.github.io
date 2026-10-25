```html
---
layout: page
title: Academic Background
permalink: /academic-background/
nav: true
nav_order: 3
---

<style>

html{
  scrollbar-gutter:stable;
}

.academic-background{
  max-width:none;
  margin:0;
}

.academic-section{
  margin-top:2.5rem;
  margin-bottom:2.8rem;
}

.academic-section h2{
  color:#333;
  font-size:1.85rem;
  font-weight:600;
  border-bottom:1px solid #d8d8d8;
  padding-bottom:.35rem;
  margin-bottom:1.5rem;
  max-width:100%;
}

.academic-item{
  display:grid;
  grid-template-columns:150px 1fr;
  column-gap:1.8rem;
  margin-bottom:2rem;
  max-width:900px;
}

.academic-date{
  color:#666;
  font-size:.95rem;
  padding-top:.15rem;
  white-space:nowrap;
}

.academic-title{
  font-size:1.08rem;
  font-weight:600;
  color:#111;
  margin-bottom:.18rem;
}

.academic-place{
  font-size:1rem;
  color:#222;
  line-height:1.55;
}

.academic-note{
  color:#666;
  font-size:.96rem;
  line-height:1.55;
}

@media (max-width:768px){

.academic-item{
  grid-template-columns:1fr;
  row-gap:.3rem;
  max-width:100%;
}

.academic-date{
  padding-top:0;
  margin-bottom:.15rem;
}

}

/* ========================================
   DARK MODE COMPATIBILITY
   ======================================== */

/* Section headings */
html[data-theme="dark"] .academic-section h2,
body[data-theme="dark"] .academic-section h2,
html.dark .academic-section h2,
body.dark .academic-section h2 {
  color:#f5f5f5 !important;
  border-bottom-color:#555 !important;
}

/* Dates */
html[data-theme="dark"] .academic-date,
body[data-theme="dark"] .academic-date,
html.dark .academic-date,
body.dark .academic-date {
  color:#bcbcbc !important;
}

/* Academic titles */
html[data-theme="dark"] .academic-title,
body[data-theme="dark"] .academic-title,
html.dark .academic-title,
body.dark .academic-title {
  color:#f5f5f5 !important;
}

/* Institutions and departments */
html[data-theme="dark"] .academic-place,
body[data-theme="dark"] .academic-place,
html.dark .academic-place,
body.dark .academic-place {
  color:#e0e0e0 !important;
}

/* Advisors and additional notes */
html[data-theme="dark"] .academic-note,
body[data-theme="dark"] .academic-note,
html.dark .academic-note,
body.dark .academic-note {
  color:#bcbcbc !important;
}

/* System dark mode fallback */
@media (prefers-color-scheme: dark) {

  html:not([data-theme]):not(.light) .academic-section h2 {
    color:#f5f5f5 !important;
    border-bottom-color:#555 !important;
  }

  html:not([data-theme]):not(.light) .academic-date {
    color:#bcbcbc !important;
  }

  html:not([data-theme]):not(.light) .academic-title {
    color:#f5f5f5 !important;
  }

  html:not([data-theme]):not(.light) .academic-place {
    color:#e0e0e0 !important;
  }

  html:not([data-theme]):not(.light) .academic-note {
    color:#bcbcbc !important;
  }

}

</style>

<div class="academic-background">

<div class="academic-section">

<h2>Professional Experience</h2>

<div class="academic-item">

<div class="academic-date">
2021.09 – Present
</div>

<div>

<div class="academic-title">
Postdoctoral Researcher
</div>

<div class="academic-place">
Department of Medical Engineering
</div>

<div class="academic-place">
California Institute of Technology (Caltech)
</div>

<div class="academic-note">
Advisor: Prof. Wei Gao
</div>
<div class="academic-note">
Co-advisor: Prof. Jinmyoung Joo (UNIST)
</div>

</div>

</div>


<div class="academic-item">

<div class="academic-date">
2019.09 – 2021.08
</div>

<div>

<div class="academic-title">
Postdoctoral Researcher
</div>

<div class="academic-place">
Chemical and Biological Integrative Research Center
</div>

<div class="academic-place">
Korea Institute of Science and Technology (KIST)
</div>

<div class="academic-note">
Advisor: Dr. Sehoon Kim
</div>

</div>

</div>

</div>

<div class="academic-section">

<h2>Education</h2>

<div class="academic-item">

<div class="academic-date">
2014.03 – 2019.08
</div>

<div>

<div class="academic-title">
Ph.D., Chemical Engineering
</div>

<div class="academic-place">
Pohang University of Science and Technology (POSTECH)
</div>

<div class="academic-note">
Advisor: Prof. Shi-Woo Rhee
</div>


</div>

</div>

<div class="academic-item">

<div class="academic-date">
2010.03 – 2014.02
</div>

<div>

<div class="academic-title">
B.S., Chemical Engineering
</div>

<div class="academic-place">
Pohang University of Science and Technology (POSTECH)
</div>

<div class="academic-note">
Magna cum laude
</div>

</div>

</div>

</div>

</div>
```
