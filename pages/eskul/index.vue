<template>
  <div class="container mx-auto py-8">
    <h1 class="text-4xl font-bold text-center mb-8">Ekstrakulikuler</h1>

    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
      <div v-for="image in images" :key="image.id" class="card bg-base-100 shadow-md cursor-pointer">
        <figure>
          <img :src="image.src" class="w-full h-48 object-cover" />
        </figure>
        <div class="card-body p-4">
          <h2 class="text-lg font-semibold text-center">{{ image.title }}</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import img1 from '../assets/eks/basket.jpg'
import img2 from '../assets/eks/bola.jpeg'
import img3 from '../assets/eks/futsal.jpeg'
import img4 from '../assets/eks/irma.jpg'
import img5 from '../assets/eks/paskib.jpeg'
import img6 from '../assets/eks/perisai.jpg'
import img7 from '../assets/eks/pks.jpg'
import img8 from '../assets/eks/pramuka.jpg'
import img9 from '../assets/eks/safe.jpg'
import img10 from '../assets/eks/voli.jpg'



const images = [
  { id: 1, title: "Basket", src: img1, alt: "Foto 1" },
  { id: 2, title: "Bola", src: img2, alt: "Foto 2" },
  { id: 3, title: "Futsal", src: img3, alt: "Foto 3" },
  { id: 4, title: "Irma", src: img4, alt: "Foto 4" },
  { id: 5, title: "Paskibra", src: img5, alt: "Foto 5" },
  { id: 6, title: "Perisai Diri", src: img6, alt: "Foto 6" },
  { id: 7, title: "PKS", src: img7, alt: "Foto 7" },
  { id: 8, title: "Pramuka", src: img8, alt: "Foto 8" },
  { id: 9, title: "Safe Riding", src: img9, alt: "Foto 9" },
  { id: 10, title: "Voli", src: img10, alt: "Foto 10" },
];
</script>
