---
layout: default
title: CV
permalink: /cv/
---
<article class="page">
  <div class="cv-head">
    <h1 class="page-title">Curriculum Vitae</h1>
    <a class="btn btn-primary" href="{{ site.cv_pdf | relative_url }}" download>
      <svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 4v11M7 10l5 5 5-5M5 20h14"/></svg>
      Download PDF
    </a>
  </div>
  <div class="cv-frame">
    <iframe src="{{ site.cv_pdf | relative_url }}#view=FitH" title="Curriculum Vitae of {{ site.author.name }}" loading="lazy"></iframe>
  </div>
  <p class="cv-fallback">If the preview does not load on your device, <a href="{{ site.cv_pdf | relative_url }}">open the PDF directly</a>.</p>
</article>
