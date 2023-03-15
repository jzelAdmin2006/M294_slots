<script setup>
import { ref } from 'vue'
import Gallery from './components/Gallery.vue'
import GalleryImage from './components/GalleryImage.vue'
import GalleryVideo from './components/GalleryVideo.vue'

const components = ref({
  image: GalleryImage,
  video: GalleryVideo
})

const galleries = ref([
  {
    id: 1,
    title: 'Beispielgalerie A',
    description: 'Ein kurzer Beschreibungstext',
    items: [
      { id: 1, type: 'image', src: 'https://unsplash.it/640/425?hash=a1', description: "Der Beschreibungstext zum Bild" },
      { id: 2, type: 'image', src: 'https://unsplash.it/640/425?hash=b1', description: "Der Beschreibungstext zum Bild" },
      { id: 3, type: 'image', src: 'https://unsplash.it/640/425?hash=c1', description: "Der Beschreibungstext zum Bild" },
      { id: 4, type: 'image', src: 'https://unsplash.it/640/425?hash=d1', description: "Der Beschreibungstext zum Bild" },
      { id: 5, type: 'video', src: 'https://www.youtube.com/embed/EkhFza9IhrM?controls=0', description: "Der Beschreibungstext zum Video" },
      { id: 6, type: 'image', src: 'https://unsplash.it/640/425?hash=f1', description: "Der Beschreibungstext zum Bild" },
      { id: 7, type: 'image', src: 'https://unsplash.it/640/425?hash=g1', description: "Der Beschreibungstext zum Bild" },
      { id: 8, type: 'image', src: 'https://unsplash.it/640/425?hash=h1', description: "Der Beschreibungstext zum Bild" },
      { id: 9, type: 'image', src: 'https://unsplash.it/640/425?hash=i1', description: "Der Beschreibungstext zum Bild" },
      { id: 10, type: 'video', src: 'https://www.youtube.com/embed/EkhFza9IhrM?controls=0', description: "Der Beschreibungstext zum Video" },
      { id: 11, type: 'image', src: 'https://unsplash.it/640/425?hash=k1', description: "Der Beschreibungstext zum Bild" },
      { id: 12, type: 'image', src: 'https://unsplash.it/640/425?hash=l1', description: "Der Beschreibungstext zum Bild" },
      { id: 13, type: 'image', src: 'https://unsplash.it/640/425?hash=m1', description: "Der Beschreibungstext zum Bild" },
      { id: 14, type: 'image', src: 'https://unsplash.it/640/425?hash=n1', description: "Der Beschreibungstext zum Bild" },
    ]
  },
  {
    id: 2,
    title: 'Beispielgalerie B',
    description: 'Ein anderer Beschreibungstext',
    items: [
      { id: 1, type: 'image', src: 'https://unsplash.it/640/425?hash=a2', description: "Der Beschreibungstext zum Bild" },
      { id: 2, type: 'image', src: 'https://unsplash.it/640/425?hash=b2', description: "Der Beschreibungstext zum Bild" },
      { id: 3, type: 'image', src: 'https://unsplash.it/640/425?hash=c2', description: "Der Beschreibungstext zum Bild" },
      { id: 4, type: 'video', src: 'https://www.youtube.com/embed/EkhFza9IhrM?controls=0', description: "Der Beschreibungstext zum Video" },
      { id: 5, type: 'image', src: 'https://unsplash.it/640/425?hash=e2', description: "Der Beschreibungstext zum Bild" },
      { id: 6, type: 'image', src: 'https://unsplash.it/640/425?hash=f2', description: "Der Beschreibungstext zum Bild" },
      { id: 7, type: 'image', src: 'https://unsplash.it/640/425?hash=g2', description: "Der Beschreibungstext zum Bild" },
      { id: 8, type: 'image', src: 'https://unsplash.it/640/425?hash=h2', description: "Der Beschreibungstext zum Bild" },
      { id: 9, type: 'image', src: 'https://unsplash.it/640/425?hash=i2', description: "Der Beschreibungstext zum Bild" },
      { id: 10, type: 'image', src: 'https://unsplash.it/640/425?hash=j2', description: "Der Beschreibungstext zum Bild" },
      { id: 11, type: 'image', src: 'https://unsplash.it/640/425?hash=k2', description: "Der Beschreibungstext zum Bild" },
      { id: 12, type: 'image', src: 'https://unsplash.it/640/425?hash=l2', description: "Der Beschreibungstext zum Bild" },
      { id: 13, type: 'video', src: 'https://www.youtube.com/embed/EkhFza9IhrM?controls=0', description: "Der Beschreibungstext zum Video" },
      { id: 14, type: 'image', src: 'https://unsplash.it/640/425?hash=n2', description: "Der Beschreibungstext zum Bild" },
    ]
  }
])
</script>

<template>
  <div class="container">
    <Gallery v-for="gallery in galleries" :key="gallery.id" :title="gallery.title" :description="gallery.description">
      <div v-for="item in gallery.items" :key="item.id">
        <component :key="item.id" :is="components[item.type]" :src="item.src" :description="item.description" />
      </div>
    </Gallery>
  </div>
</template>

<style>
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