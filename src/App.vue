<script setup>
import { ref } from 'vue'

const galleries = ref([
  {
    title: 'Beispielgalerie A',
    description: 'Ein kurzer Beschreibungstext',
    items: [
      { type: 'image', src: 'https://unsplash.it/640/425?hash=a1', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=b1', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=c1', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=d1', description: "Der Beschreibungstext zum Bild"},
      { type: 'video', src: 'https://www.youtube.com/embed/EkhFza9IhrM?controls=0', description: "Der Beschreibungstext zum Video"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=f1', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=g1', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=h1', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=i1', description: "Der Beschreibungstext zum Bild"},
      { type: 'video', src: 'https://www.youtube.com/embed/EkhFza9IhrM?controls=0', description: "Der Beschreibungstext zum Video"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=k1', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=l1', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=m1', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=n1', description: "Der Beschreibungstext zum Bild"},
    ]
  },
  {
    title: 'Beispielgalerie B',
    description: 'Ein anderer Beschreibungstext',
    items: [
      { type: 'image', src: 'https://unsplash.it/640/425?hash=a2', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=b2', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=c2', description: "Der Beschreibungstext zum Bild"},
      { type: 'video', src: 'https://www.youtube.com/embed/EkhFza9IhrM?controls=0', description: "Der Beschreibungstext zum Video"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=e2', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=f2', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=g2', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=h2', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=i2', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=j2', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=k2', description: "Der Beschreibungstext zum Bild"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=l2', description: "Der Beschreibungstext zum Bild"},
      { type: 'video', src: 'https://www.youtube.com/embed/EkhFza9IhrM?controls=0', description: "Der Beschreibungstext zum Video"},
      { type: 'image', src: 'https://unsplash.it/640/425?hash=n2', description: "Der Beschreibungstext zum Bild"},
    ]
  }
])
</script>

<template>
  <div class="container">

    <section class="gallery">
      <h2 class="gallery__title">
        Titel der Galerie
      </h2>
      <p class="gallery__description">
        Beschreibungstext
      </p>
      <div class="gallery__images">

        <!-- Bild -->
        <div class="image">
          <img class="image__img" src="https://unsplash.it/640/425?hash=g2" alt=""/>
          <p class="image__description">
            Bildbeschreibung
          </p>
        </div>

        <!-- Video -->
        <div class="video">
          <iframe
              class="video__iframe"
              width="640"
              height="425"
              src="https://www.youtube.com/embed/EkhFza9IhrM?controls=0"
              title="YouTube video player"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
              allowfullscreen
          ></iframe>
          <div class="video__description">
            Beschreibung zum Video
          </div>
        </div>

      </div>
    </section>
  </div>
</template>

<style>
/** Gallery **/
.gallery + .gallery {
  margin-top: 4rem;
}

.gallery__title {
  font-weight: bold;
  font-size: 2rem;
  margin: 1rem 0;
  padding: 0;
}

.gallery__description {
  margin: 0;
  padding: 0;
  font-size: 1rem;
}

.gallery__images {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  grid-gap: 1rem;
  margin: 1rem 0;
}

/** Bild **/
.image__img {
  aspect-ratio: 640/425;
  max-width: 100%;
  height: auto;
  object-fit: cover;
  display: block;
}

.image__description {
  color: #9ca3af;
  font-size: .85rem;
  margin-top: 1rem;
}

/** Video **/
.video__iframe {
  aspect-ratio: 640/425;
  max-width: 100%;
  height: auto;
  border: none;
}

.video__description {
  color: #9ca3af;
  font-size: .85rem;
  margin-top: 1rem;
}
</style>
