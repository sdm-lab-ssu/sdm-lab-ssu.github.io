---
layout: page
title: Publications
subtitle:
---

<style>
  /* Adjust the page width just for this page alone. */
  .container-md {
    max-width: 1800px; /* Set your desired maximum width */
    margin-left: auto;
    margin-right: auto;
  }

  /* Add any other custom styles for the page */
  body {
    margin: 0; /* Set margin to 0 for the entire body */
  }
</style>

You can also find publications on <a href="https://scholar.google.com/citations?user=0Xzd2f8AAAAJ">Google Scholar</a> which may include some preprints not yet listed here.

**Journal Papers**

<!-- Just make a table and iterate through publications. -->
<table cellpadding="10" width="100%">
    {% for pub in site.data.pubs %}
        {% include pub.html %}
    {% endfor %}
</table>

<!-- Daniel: doing this to add a separate workshop publication section. -->
<div style="height: 40px;"></div>

**Workshop Papers**

<!--Daniel: uses the same pub.html, but a different data.workshop_pubs -->
<table cellpadding="10" width="100%">
    {% for pub in site.data.workshop_pubs %}
        {% include pub.html %}
    {% endfor %}
</table>

<script>
(function () {
  const DEFAULT_SCALE = 2.5;     // 기본 2배
  const PADDING = 16;          // 커서와 미리보기 사이 간격

  let preview = null;

  function onEnter(e) {
    const img = e.currentTarget;
    const rect = img.getBoundingClientRect();
    const scale = parseFloat(img.dataset.scale || DEFAULT_SCALE);

    // 미리보기 이미지 생성
    preview = document.createElement('img');
    preview.src = img.currentSrc || img.src;
    preview.alt = img.alt || 'preview';
    preview.style.position = 'fixed';
    preview.style.pointerEvents = 'none';
    preview.style.zIndex = '9999';
    preview.style.boxShadow = '0 10px 30px rgba(0,0,0,.35)';
    preview.style.borderRadius = '6px';
    preview.style.background = '#fff';
    preview.style.width = Math.round(rect.width * scale) + 'px';
    preview.style.maxWidth = (window.innerWidth * 0.9) + 'px';
    preview.style.maxHeight = (window.innerHeight * 0.9) + 'px';
    preview.style.transition = 'opacity .08s ease';
    preview.style.opacity = '0';

    document.body.appendChild(preview);
    // 약간의 지연 후 보여주기 (부드럽게)
    requestAnimationFrame(() => { if (preview) preview.style.opacity = '1'; });
  }

  function onMove(e) {
    if (!preview) return;

    const vw = window.innerWidth, vh = window.innerHeight;
    const pw = preview.naturalWidth ? preview.width : preview.getBoundingClientRect().width;
    const ph = preview.naturalHeight ? preview.height : preview.getBoundingClientRect().height;

    // 기본 위치: 커서 오른쪽-아래
    let x = e.clientX + PADDING;
    let y = e.clientY + PADDING;

    // 화면을 넘치면 좌/상단으로 뒤집기
    if (x + pw > vw - 8) x = e.clientX - pw - PADDING;
    if (y + ph > vh - 8) y = e.clientY - ph - PADDING;

    preview.style.left = x + 'px';
    preview.style.top  = y + 'px';
  }

  function onLeave() {
    if (preview) {
      preview.remove();
      preview = null;
    }
  }

  function bind() {
    document.querySelectorAll('img.js-hover-zoom').forEach(img => {
      img.addEventListener('mouseenter', onEnter);
      img.addEventListener('mousemove', onMove);
      img.addEventListener('mouseleave', onLeave);
      // 스크롤 시에는 미리보기 제거
      img.addEventListener('scroll', onLeave, { passive: true });
    });
    // 페이지 스크롤/리사이즈 시에도 안전하게 제거
    window.addEventListener('scroll', onLeave, { passive: true });
    window.addEventListener('resize', onLeave);
  }

  if (document.readyState === 'loading') {
    document.addEventListener('DOMContentLoaded', bind);
  } else {
    bind();
  }
})();
</script>
