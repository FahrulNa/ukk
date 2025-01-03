<template>
  <div class=" container mx-auto py-8">
    <h1 class="text-4xl font-bold text-center mb-8">Galeri </h1>
    
    <!-- Grid Galeri -->
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
      <div 
        v-for="image in images" 
        :key="image.id" 
        class="card bg-base-100 shadow-md cursor-pointer"
        @click="openModal(image)"
      >
        <figure>
          <img :src="image.src" :alt="image.alt" class="w-full h-48 object-cover" />
        </figure>
        <div class="card-body p-4">
          <h2 class="text-lg font-semibold text-center">{{ image.title }}</h2>
        </div>
      </div>
    </div>

    <!-- Modal -->
    <div v-if="selectedImage" class="modal modal-open">
      <div class="modal-box relative">
        <button @click="closeModal" class="btn btn-sm btn-circle absolute right-2 top-2">✕</button>
        <figure>
          <img :src="selectedImage.src" :alt="selectedImage.alt" class="w-full" />
        </figure>
        <h2 class="text-lg font-semibold text-center mt-4">{{ selectedImage.title }}</h2>
      </div>
    </div>
  </div>
</template>

<script setup>
import img from '../assets/galeri/b.jpg'

const images = [
  { id: 1, title: "Foto 1", src: img, alt: "Foto 1" },
  { id: 2, title: "Foto 2", src: img, alt: "Foto 2" },
  { id: 3, title: "Foto 3", src: img, alt: "Foto 3" },
  { id: 4, title: "Foto 4", src: img, alt: "Foto 4" },
  { id: 5, title: "Foto 5", src: img, alt: "Foto 5" },
  { id: 6, title: "Foto 6", src: img, alt: "Foto 6" },
  { id: 7, title: "Foto 7", src: img, alt: "Foto 7" },
  { id: 8, title: "Foto 8", src: img, alt: "Foto 8" },
];

const selectedImage = ref(null);

const openModal = (image) => {
  selectedImage.value = image;
};

const closeModal = () => {
  selectedImage.value = null;
};
</script>
