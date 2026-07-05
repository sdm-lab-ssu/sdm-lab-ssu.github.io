---
layout: page
title: Lab Photos
subtitle:
permalink: /photos/
---

<div id="photos-page">

  <!-- Event cards -->
  <div class="photo-events-grid">
    {% for event in site.data.photos %}
    <div class="photo-event-card" onclick="openGallery('{{ event.id }}')">
      <div class="photo-event-thumb">
        <img src="/img/photos/{{ event.id }}/{{ event.photos[0].file }}" alt="{{ event.title_kr }}">
      </div>
      <div class="photo-event-info">
        <h3>{{ event.title_kr }}</h3>
        <p>{{ event.date }} &middot; {{ event.photos | size }}장</p>
      </div>
    </div>
    {% endfor %}
  </div>

  <!-- Modals -->
  {% for event in site.data.photos %}
  <div class="gallery-modal" id="gallery-{{ event.id }}">
    <div class="gallery-modal-backdrop" onclick="closeGallery('{{ event.id }}')"></div>
    <div class="gallery-modal-content">
      <div class="gallery-modal-header">
        <h2>{{ event.title_kr }}</h2>
        <button class="gallery-modal-close" onclick="closeGallery('{{ event.id }}')">&times;</button>
      </div>
      <p class="gallery-date">{{ event.title }} &middot; {{ event.date }}</p>
      <div class="gallery-modal-grid">
        {% for photo in event.photos %}
        <div class="gallery-modal-item">
          <img src="/img/photos/{{ event.id }}/{{ photo.file }}"
               alt="{{ photo.caption | default: event.title_kr }}"
               onclick="openLightbox(this, '{{ photo.caption | default: '' }}')"
               class="gallery-thumb">
          {% if photo.caption and photo.caption != "" %}
          <p class="gallery-modal-caption">{{ photo.caption }}</p>
          {% endif %}
        </div>
        {% endfor %}
      </div>
    </div>
  </div>
  {% endfor %}

  <!-- Lightbox -->
  <div id="lightbox" onclick="closeLightbox()">
    <button id="lightbox-close" onclick="closeLightbox()">&times;</button>
    <img id="lightbox-img" src="" alt="">
    <p id="lightbox-caption"></p>
  </div>

</div>

<script>
function openGallery(id) {
  document.getElementById('gallery-' + id).classList.add('open');
  document.body.style.overflow = 'hidden';
}
function closeGallery(id) {
  document.getElementById('gallery-' + id).classList.remove('open');
  document.body.style.overflow = '';
}
function openLightbox(imgEl, caption) {
  event.stopPropagation();
  var lb = document.getElementById('lightbox');
  document.getElementById('lightbox-img').src = imgEl.src;
  var cap = document.getElementById('lightbox-caption');
  cap.textContent = caption;
  cap.style.display = caption ? 'block' : 'none';
  lb.classList.add('open');
}
function closeLightbox() {
  document.getElementById('lightbox').classList.remove('open');
}
document.addEventListener('keydown', function(e) {
  if (e.key === 'Escape') {
    closeLightbox();
    document.querySelectorAll('.gallery-modal.open').forEach(function(m) {
      m.classList.remove('open');
    });
    document.body.style.overflow = '';
  }
});
</script>
