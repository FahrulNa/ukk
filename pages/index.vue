<template>
  <div class="carousel w-full h-full z-20 relative">
    <!-- Carousel Items -->
    <div v-for="(item, index) in items" :key="index"
      :class="['carousel-item w-full', { 'active': currentSlide === index }]"
      style="transition: transform 0.5s ease-in;">
      <!-- Background Image -->
      <img :src="item.img" class="w-full h-[80vh] opacity-80 object-cover" />

      <!-- Text Content -->
      <div class="absolute inset-0 flex flex-col items-center justify-center text-center text-white z-10 px-4">
        <h1 class="text-4xl md:text-5xl font-bold mb-4">{{ item.title }}</h1>
        <p class="text-base md:text-lg max-w-2xl">"{{ item.description }}"</p>
      </div>

    </div>

    <!-- Previous Button -->
    <button
      class="prev group absolute top-1/2 left-4 transform -translate-y-1/2 border border-white text-white hover:bg-[#11224e] hover:text-white flex p-2 rounded-full z-20"
      @click="prevSlide">
      <Icon name="material-symbols:arrow-left-alt-rounded" size="2rem" class="group-hover:scale-75" />
    </button>

    <!-- Next Button -->
    <button
      class="next group absolute top-1/2 right-4 transform -translate-y-1/2 border border-white text-white hover:bg-[#11224e] hover:text-white flex p-2 rounded-full z-20"
      @click="nextSlide">
      <Icon name="material-symbols:arrow-right-alt-rounded" size="2rem" class="group-hover:scale-75" />
    </button>
  </div>

  <div class="hero paddingX bg-gradient-to-r from-blue-900 via-blue-700 to-blue-500 min-h-screen text-white">
    <div class="hero-content">
      <div class="flex-cols">
        <img src="../assets/img/kepsek.png" class="max-w-sm rounded-lg shadow-2xl" />
        <div
          class="Text text-center font-bold bg-blue-800  text-white rounded-lg py-2 leading-3">
          <p class="tracking-wide text-2xl">Kurniawan, S.Pd., M.Pd.</p>
          <p class="tracking-wide text-lg">Kepala Sekolah</p>
        </div>
      </div>
      <div class="ml-4">
        <h1 class="text-5xl font-bold mb-4">Sambutan Kepala Sekolah</h1>
        <p>Assalamu'alaikum Wr, Wb</p>
        <br />
        <p class="text-justify">
          Puji syukur kita panjatkan ke hadirat Allah SWT atas limpahan rahmat dan karunia-Nya, sehingga SMKN
          4
          Tasikmalaya dapat terus berkiprah dalam mencetak generasi muda yang unggul, berkarakter, dan siap
          bersaing
          di dunia kerja maupun melanjutkan pendidikan ke jenjang yang lebih tinggi.
        </p>
        <br />
        <p class="text-justify">
          Selamat datang di situs resmi SMKN 4 Tasikmalaya, sebuah media informasi yang kami persembahkan
          untuk
          memberikan gambaran menyeluruh mengenai sekolah kami. Situs ini dirancang untuk memudahkan akses
          informasi
          bagi seluruh siswa, orang tua, alumni, dan masyarakat luas.
        </p>
      </div>
    </div>
  </div>

  <div class="hero paddingX min-h-screen text-black">
    <div class="hero-content flex-col lg:flex-row-reverse">
      <img src="../assets/img/d.jpg " class="max-w-sm rounded-lg shadow-2xl" />
      <div>
        <h1 class="text-5xl font-bold">Sejarah Sekolah</h1>
        <p class="py-6 text-justify">
          Sejalan dengan Program Pemerintah dibidang pendidikan Menengah Kejuruan pada saat itu yakni
          pemerataan akses ditambah pula dengan banyaknya keinginan masyarakat yang mengharapkan adanya SMK
          Negeri di daerah Kecamatan Purbaratu Kota Tasikmalaya terutama untuk menampung tamatan dari SLTP
          yang ingin melanjutkan ke SMK maka beberapa tokoh masyarakat, unsur pejabat pemerintah di Kecamatan
          Purbaratu Kota Tasikmalaya mengusulkan kepada pemerintah Kota Tasikmalaya dan Pemerintah Provinsi
          Jawa Barat, agar berdirinya SMK Negeri di Kecamatan Purbaratu Kota Tasikmalaya.
        </p>
        <NuxtLink to="../sejarah">
          <button class="btn bg-[#eee]">
            <p class="">Lihat Selengkapnya</p>
          </button>
        </NuxtLink>
      </div>
    </div>
  </div>
  <div class="container mx-auto p-4">
    <div class="card bg-base-100 shadow-xl">
      <!-- Judul -->
      <div class="bg-gray-100 py-4 text-center border-b">
        <h1 class="text-xl font-bold">Statistik Data</h1>
      </div>

      <!-- Grid Statistik -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-4 p-6 bg-base-100">
        <!-- Jumlah Siswa -->
        <div class="card bg-blue-100 shadow p-4">
          <div class="text-center">
            <h2 class="text-lg font-semibold">Jumlah Siswa</h2>
            <p class="text-4xl font-bold">{{ jumlahSiswa }}</p>
          </div>
        </div>

        <!-- Jumlah Rombel -->
        <div class="card bg-blue-100 shadow p-4">
          <div class="text-center">
            <h2 class="text-lg font-semibold">Jumlah Rombel</h2>
            <p class="text-4xl font-bold">{{ jumlahRombel }}</p>
          </div>
        </div>

        <!-- Jumlah Guru -->
        <div class="card bg-blue-100 shadow p-4">
          <div class="text-center">
            <h2 class="text-lg font-semibold">Jumlah Guru</h2>
            <p class="text-4xl font-bold">{{ jumlahGuru }}</p>
          </div>
        </div>

        <!-- Jumlah Tenaga Administrasi -->
        <div class="card bg-blue-100 shadow p-4">
          <div class="text-center">
            <h2 class="text-lg font-semibold">Jumlah Tenaga Administrasi</h2>
            <p class="text-4xl font-bold">{{ jumlahTenagaAdministrasi }}</p>
          </div>
        </div>
      </div>
      <div class="flex justify-center mb-2">
        <NuxtLink to="../datastatistik">
          <button class="btn text-center flex">Selengkapnya...</button>
        </NuxtLink>
      </div>
    </div>
    <!-- Grid Berita -->
    <div class="card bg-base-100 shadow-xl mt-5">
      <div class="container mx-auto py-8">
        <h1 class="text-4xl font-bold text-center mb-8">Berita Terkini</h1>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="news in displayedNews" :key="news.id" class="card bg-base-100 shadow-xl">
            <figure>
              <img :src="news.image" :alt="news.title" class="w-full h-48 object-cover" />
            </figure>
            <div class="card-body">
              <h2 class="card-title">{{ news.title }}</h2>
              <p>{{ news.summary }}</p>
            </div>
          </div>
        </div>
      </div>
      <div class="flex justify-center mb-2">
        <NuxtLink to="../berita">
          <button class="btn text-center flex">Berita Lainnya...</button>
        </NuxtLink>
      </div>
    </div>
    <!-- Grid Berita -->
    <div class="card bg-base-100 shadow-xl mt-5">
      <div class="container mx-auto py-8">
        <h1 class="text-4xl font-bold text-center mb-8">Galeri</h1>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <div v-for="galeri in displayedGaleri" :key="galeri.id" class="card bg-base-100 shadow-xl">
            <figure>
              <img :src="galeri.image" :alt="galeri.title" class="w-full h-48 object-cover" />
            </figure>
            <div class="card-body">
              <h2 class="card-title">{{ galeri.title }}</h2>
              <p>{{ galeri.summary }}</p>
            </div>
          </div>
        </div>
      </div>
      <div class="flex justify-center mb-2">
        <NuxtLink to="../galeri">
          <button class="btn text-center flex">Selengkapnya</button>
        </NuxtLink>
      </div>
    </div>
  </div>
</template>

<script setup>
import images1 from '../assets/img/gerbangsmk.png';
// import images4 from '../assets/img/TP.jpg';
// import images5 from '../assets/img/pbo.png';
import images6 from '../assets/img/lampu.jpg';
import images7 from '../assets/img/ruangkelas1.jpg';
import images8 from '../assets/galeri/b.jpg';
import images9 from '../assets/berita/astra.jpg';

//gambar carousel
const items = ref([
  { bg: images1, img: images1, title: 'Selamat Datang Di', description: 'SMK Negeri Tasikmalaya' },
  { bg: images1, img: images7, title: 'SMK Negeri 4 Tasikmalaya', description: 'TERWUJUDNYA LULUSAN YANG CERDAS, AKTIF, KOMPETITIF, ADAPTIF, DAN PRODUKTIF BERLANDASKAN IMAN DAN TAKWA' },
  { bg: images1, img: images6, title: 'Mari Bergabung Bersama Kami', description: 'Cakap dan Berimtak' },
]);

//berita
const allNews = [
  { id: 1, title: "Berita Pertama", summary: "Ini adalah ringkasan berita pertama.",image: images9 },
  { id: 2, title: "Berita Kedua", summary: "Ini adalah ringkasan berita kedua.", image: images9 },
  { id: 3, title: "Berita Ketiga", summary: "Ini adalah ringkasan berita ketiga.", image: images9  },
  { id: 4, title: "Berita Keempat", summary: "Ini adalah ringkasan berita keempat.",image: images9  },
  { id: 5, title: "Berita Kelima", summary: "Ini adalah ringkasan berita kelima.",image: images9  },
  { id: 6, title: "Berita Keenam", summary: "Ini adalah ringkasan berita keenam.", image: images9  },
];

const displayedNews = ref(allNews.slice(0, 3));

//galeri
const allGaleri = [
  { id: 1, title: "kegiatan", summary: "Ini adalah ringkasan berita pertama.", image: images8 },
  { id: 2, title: "kegiatan", summary: "Ini adalah ringkasan berita kedua.",image: images8 },
  { id: 3, title: "kegiatan", summary: "Ini adalah ringkasan berita ketiga.", image: images8 },
  { id: 4, title: "kegiatan", summary: "Ini adalah ringkasan berita keempat.", image: images8 },
  { id: 5, title: "kegiatan", summary: "Ini adalah ringkasan berita kelima.", image: images8 },
  { id: 6, title: "kegiatan", summary: "Ini adalah ringkasan berita keenam.", image: images8 },
];

const displayedGaleri = allGaleri

// Data untuk statistik
const jumlahSiswa = 1459;
const jumlahRombel = 34;
const jumlahGuru = 60;
const jumlahTenagaAdministrasi = 10;


const currentSlide = ref(0);
let interval = null;


const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % items.value.length;
};

const prevSlide = () => {
  currentSlide.value = (currentSlide.value - 1 + items.value.length) % items.value.length;
};



</script>

<style scoped>
.carousel-item {
  display: none;
}

.carousel-item.active {
  display: block;
}
</style>