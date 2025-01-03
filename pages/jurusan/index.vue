<template>
  <div class="card bg-base-100 shadow-xl mt-5">
    <div class="container mx-auto py-8">
      <h1 class="text-4xl font-bold text-center mb-8">Jurusan</h1>

      <!-- Grid Berita -->
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div v-for="jurusan in displayedjurusan" :key="jurusan.id" class="card bg-base-100 shadow-xl">
          <figure>
            <img :src="jurusan.image" :alt="jurusan.title" class="w-full max-h-screen object-cover " />
          </figure>
          <div class="card-body">
            <h2 class="card-title">{{ jurusan.title }}</h2>
            <p>{{ jurusan.summary }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup>
//jurusan

import images1 from '../assets/jurusan/tjkt.jpg'
import images2 from '../assets/jurusan/tbsm.jpg'
import images3 from '../assets/jurusan/pplg.jpg'
import images4 from '../assets/jurusan/dkv.jpg'
import images5 from '../assets/jurusan/toi.jpg'


const allJurusan = [
  { id: 1, title: "TBSM", summary: "Ini adalah ringkasan jurusan pertama.", image: images1 },
  { id: 2, title: "TJKT", summary: "Ini adalah ringkasan jurusan kedua.", image: images2 },
  { id: 3, title: "PPLG", summary: "Ini adalah ringkasan jurusan ketiga.", image: images3 },
  { id: 4, title: "DKV", summary: "Ini adalah ringkasan jurusan keempat.", image: images4 },
  { id: 5, title: "TOI", summary: "Ini adalah ringkasan jurusan kelima.", image: images5 },
];

const displayedjurusan = allJurusan

</script>

<style></style>