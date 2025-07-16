---
layout: single
title: "Memories"
permalink: /gallery/
---

<style>
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 30px;
  margin-top: 2rem;
}

.gallery-item {
  position: relative;
  overflow: hidden;
  border-radius: 16px;
  box-shadow: 0 10px 25px rgba(0, 0, 0, 0.5);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.gallery-item:hover {
  transform: translateY(-6px);
  box-shadow: 0 16px 30px rgba(0, 0, 0, 0.6);
}

.gallery-item img {
  width: 100%;
  height: auto;
  display: block;
  border-radius: 16px;
  object-fit: cover;
}

.gallery-caption {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  background: rgba(0, 0, 0, 0.6); /* dark translucent background */
  color: #f0f0f0;
  padding: 10px 12px;
  font-size: 0.95rem;
  font-style: italic;
  text-align: center;
  backdrop-filter: blur(6px);
  border-bottom-left-radius: 16px;
  border-bottom-right-radius: 16px;
}
</style>


<div class="gallery-grid">
  {% assign sorted_gallery = site.gallery | sort: 'date' | reverse %}
  {% for photo in sorted_gallery %}
    <div class="gallery-item">
      <img src="{{ photo.image | relative_url }}" alt="{{ photo.title }}">
      <div class="gallery-caption">{{ photo.caption }}</div>
    </div>
  {% endfor %}
</div>
