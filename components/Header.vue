<template>
  <div class="relative z-50">
    <header class="bg-gradient-to-r paddingX from-blue-900 via-blue-700 to-blue-500 text-white shadow-md">
      <div class="container px-6 py-4 mx-auto flex justify-between items-center">
        <!-- Logo -->
        <div class="flex items-center space-x-2">
          <NuxtLink to="../">
            <img src="../assets/img/Logo.png" alt="Logo" class="h-[80px]" />
          </NuxtLink>
          <div class="">
            <NuxtLink to="../">
              <h1 class="text-3xl font-bold text-black">SMKN 4 Tasikmalaya</h1>
              <address> Jl. Depok Sukamenak, Purbaratu, Tasikmalaya, Jawa Barat</address>
            </NuxtLink>
          </div>

        </div>
        <div class="paddingX bg flex justify-center text-black paddingX  font-titillium gap-6 sticky py-3">
          <NuxtLink to="/">
            <p class="">Beranda</p>
          </NuxtLink>
          <div class="Profile relative inline-block group cursor-pointer">
            <div class="OnHover group flex items-center">
              <p class="">Profil</p>
              <Icon name="material-symbols:keyboard-arrow-down-rounded" class="group-hover:rotate-180" />
            </div>
            <div
              class="ListHover absolute left-0 z-10 hidden origin-top-right bg-white shadow-md w-[150px] divide-y divide-gray-100 group-hover:block group-hover:transition-all group-hover:ease-in-out group-hover:duration-300">
              <ul>
                <li class="hover:bg-slate-100 p-2">
                  <NuxtLink to="../sejarah">Sejarah</NuxtLink>
                </li>
                <li class="hover:bg-slate-100 p-2">
                  <NuxtLink to="../visimisi">Visi dan Misi</NuxtLink>
                </li>
                <li class="hover:bg-slate-100 p-2">
                  <NuxtLink to="../identitas">Identitas Sekolah</NuxtLink>
                </li>
                <li class="hover:bg-slate-100 p-2">
                  <NuxtLink to="../datastatistik">Data Statistik</NuxtLink>
                </li>
              </ul>
            </div>
          </div>
          <NuxtLink to="../berita">
            <p class="">Berita</p>
          </NuxtLink>
          <div class="Siswa relative inline-block group cursor-pointer">
            <div class="OnHover group flex items-center">
              <p class="">Siswa</p>
              <Icon name="material-symbols:keyboard-arrow-down-rounded" class="group-hover:rotate-180" />
            </div>
            <div
              class="ListHover absolute left-0 z-10 hidden origin-top-right bg-white shadow-md w-[150px] divide-y divide-gray-100 group-hover:block group-hover:transition-all group-hover:ease-in-out group-hover:duration-300">
              <ul>
                <li class="hover:bg-slate-100 p-2">
                  <NuxtLink to="../eskul">Ekstrakurikuler</NuxtLink>
                </li>
                <li class="hover:bg-slate-100 p-2">
                  <NuxtLink to="../jurusan">Kompetensi Keahlian</NuxtLink>
                </li>
              </ul>
            </div>
          </div>
          <NuxtLink to="../galeri">
            <p class="">Gallery</p>
          </NuxtLink>
        </div>
      </div>
    </header>
  </div>
</template>

<style scoped></style>