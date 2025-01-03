<template>
  <div class="container mx-auto py-8">
    <h1 class="text-4xl font-bold text-center mb-8">Berita Terkini</h1>
    
    <!-- Grid Berita -->
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      <div 
        v-for="news in displayedNews" 
        :key="news.id" 
        class="card bg-base-100 shadow-xl"
      >
        <figure>
          <img :src="news.image" :alt="news.title" class="w-full h-48 object-cover" />
        </figure>
        <div class="card-body">
          <h2 class="card-title">{{ news.title }}</h2>
          <p>{{ news.summary }}</p>
          <div class="card-actions justify-end">
            <button class="btn btn-primary">Baca Selengkapnya</button>
          </div>
        </div>
      </div>
    </div>

    <!-- Tombol Load More -->
    <div class="flex justify-center mt-8">
      <button 
        v-if="hasMoreNews" 
        @click="loadMore" 
        class="btn btn-outline btn-primary"
      >
        Load More
      </button>
      <p v-else class="text-gray-500">Semua berita sudah ditampilkan</p>
    </div>
  </div>
</template>

<script setup>
import images1 from '../assets/img/gerbangsmk.png';
// import images4 from '../assets/img/TP.jpg';
// import images5 from '../assets/img/pbo.png';
import images6 from '../assets/img/lampu.jpg';
import images7 from '../assets/galeri/b.jpg';

const allNews = [
  { id: 1, title: "Berita Pertama", summary: "Ini adalah ringkasan berita pertama.", image: images7 },
  { id: 2, title: "Berita Kedua", summary: "Ini adalah ringkasan berita kedua.", image: images7 },
  { id: 3, title: "Berita Ketiga", summary: "Ini adalah ringkasan berita ketiga.", image: images7 },
  { id: 4, title: "Berita Keempat", summary: "Ini adalah ringkasan berita keempat.", image: images7 },
  { id: 5, title: "Berita Kelima", summary: "Ini adalah ringkasan berita kelima.",image: images7 },
  { id: 6, title: "Berita Keenam", summary: "Ini adalah ringkasan berita keenam.", image: images7 },
];

const displayedNews = ref(allNews.slice(0, 3)); 
const itemsPerPage = 3;
const hasMoreNews = ref(displayedNews.value.length < allNews.length);

const loadMore = () => {
  const currentLength = displayedNews.value.length;
  const nextItems = allNews.slice(currentLength, currentLength + itemsPerPage);
  displayedNews.value = [...displayedNews.value, ...nextItems];
  hasMoreNews.value = displayedNews.value.length < allNews.length;
};
</script>