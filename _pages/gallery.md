---
layout: single
title: "Memories"
permalink: /gallery/
---

<style>
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: 24px;
  margin-top: 2rem;
}

.gallery-item {
  position: relative;
  overflow: hidden;
  border-radius: 12px;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.4);
  background-color: rgba(255, 255, 255, 0.03);
}

.gallery-item img {
  width: 100%;
  height: auto;
  display: block;
  border-radius: 12px;
  transition: transform 0.4s ease;
}

.gallery-item:hover img {
  transform: scale(1.05); /* 👈 slight zoom-in */
}

.gallery-caption {
  padding: 8px 10px;
  text-align: center;
  font-size: 0.95rem;
  font-style: italic;
  color: #f0f0f0;
  background: rgba(0, 0, 0, 0.5);
  border-bottom-left-radius: 12px;
  border-bottom-right-radius: 12px;
}
</style>


<p style="text-align: left; font-size: 1.15rem; color: #e0e0e0; margin-bottom: 2rem;">This page chronicles my journey through various natural landscapes and the cherished memories made along the way.</p>

<div class="gallery-grid">
  {% assign sorted_gallery = site.gallery | sort: 'date' | reverse %}
  {% for photo in sorted_gallery %}
    <div class="gallery-item">
      <img src="{{ photo.image | relative_url }}" alt="{{ photo.title }}">
      <div class="gallery-caption">{{ photo.caption }}</div>
    </div>
  {% endfor %}
</div>
