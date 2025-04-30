---
layout: archive
title: "Misc"
permalink: /Misc/
author_profile: true
redirect_from:
  - /Misc
---

{% include base_path %}

Nature lover
======
I'd love to roam through nature — from soaring peaks to the deepest abysses, from drifting clouds to distant stars, from endless grassland pastures to the whispering seaside. Whenever I have a holiday, I enjoy going hiking or camping.
```html
<!DOCTYPE html>
<html>
<head>
<style>
  .container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    background: #f0f0f0;
    display: grid;
    gap: 10px;
    padding: 10px;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-auto-rows: minmax(150px, auto);
  }

  .img-wrapper {
    position: relative;
    overflow: hidden;
    border-radius: 8px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
  }

  .img-wrapper img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s;
  }

  .img-wrapper:hover img {
    transform: scale(1.05);
  }
</style>
</head>
<body>

<div class="container" id="gallery"></div>

<script>
const images = [
  { url: "https://niko-kang.github.io/GOAL/images/t1.jpg" },
  { url: "https://niko-kang.github.io/GOAL/images/t2.jpg" },
  { url: "https://niko-kang.github.io/GOAL/images/t3.jpg" }
];

function createGallery() {
  const container = document.getElementById('gallery');
  
  images.forEach(img => {
    const wrapper = document.createElement('div');
    wrapper.className = 'img-wrapper';
    
    const image = new Image();
    image.src = img.url;
    
    image.onload = function() {
      const aspectRatio = this.naturalWidth / this.naturalHeight;
      if (aspectRatio > 1) {
        wrapper.style.gridColumn = 'span 2';
      } else {
        wrapper.style.gridRow = 'span 2';
      }
    };
    
    wrapper.appendChild(image);
    container.appendChild(wrapper);
  });
}

window.addEventListener('resize', () => {
  document.querySelectorAll('.img-wrapper').forEach(wrapper => {
    const img = wrapper.querySelector('img');
    const aspectRatio = img.naturalWidth / img.naturalHeight;
    
    if (window.innerWidth > 768) {
      wrapper.style.gridColumn = aspectRatio > 1 ? 'span 2' : '';
      wrapper.style.gridRow = aspectRatio <= 1 ? 'span 2' : '';
    } else {
      wrapper.style.gridColumn = '';
      wrapper.style.gridRow = '';
    }
  });
});

createGallery();
</script>

</body>
</html>
```

Music
======
I find great joy in the world of music, embracing genres such as electronic, jazz, and classical music. I began learning the piano at the age of five and later pursued training in singing, with a focus on national vocal music.

Sport
======
Every two weeks, I watch Formula 1 races. I also make time for weekly workouts and love riding road bikes during my free time.
