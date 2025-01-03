<template>
  <div class="container mx-auto p-4">
    <div class="card bg-base-100 shadow-xl">
      <!-- Judul -->
      <div class="bg-gray-100 py-4 text-center border rounded-md">
        <div class="breadcrumbs text-sm">
          <ul class="ml-2 text-lg">
            <li><a href="../">Home</a></li>
            <li>Data Statistik</li>
          </ul>
        </div>
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
    </div>
    <!-- Card Induk -->
    <div class="card bg-base-100 shadow-xl p-6">

      <!-- Grid Layout untuk Semua Card -->
      <div class="grid grid-cols-1 md:grid-cols-2 gap-8 justify-items-center">
        <!-- Bar Chart -->
        <div class="card bg-base-100 shadow-lg p-6 max-w-md w-full">
          <h2 class="text-lg font-bold mb-24 text-center">Rekap Tingkat Pendidikan Siswa</h2>
          <Bar :data="barChartData" :options="barChartOptions" />
        </div>

        <!-- Pie Chart: Jenis Kelamin Siswa -->
        <div class="card bg-base-100 shadow-lg p-6 max-w-md w-full">
          <h2 class="text-lg font-bold mb-4 text-center">Rekap Jenis Kelamin Siswa</h2>
          <Pie :data="genderPieChartData" :options="pieChartOptions" />
        </div>

        <!-- Pie Chart: Status Kepegawaian Pendidik -->
        <div class="card bg-base-100 shadow-lg p-6 max-w-md w-full">
          <h2 class="text-lg font-bold mb-4 text-center">Status Kepegawaian Pendidik</h2>
          <Pie :data="employmentPieChartData" :options="pieChartOptions" />
        </div>

      </div>
    </div>
  </div>
</template>

<script setup>
// Data untuk statistik
const jumlahSiswa = 1116;
const jumlahRombel = 34;
const jumlahGuru = 60;
const jumlahTenagaAdministrasi = 10;


//chart//
import { Bar, Pie } from 'vue-chartjs';

// Data untuk Bar Chart (Rekap Tingkat Pendidikan Siswa)
const barChartData = {
  labels: ["Tingkat 10", "Tingkat 11", "Tingkat 12"],
  datasets: [
    {
      label: "Laki-laki",
      backgroundColor: "#4A90E2",
      data: [200, 250, 220], // Contoh data
    },
    {
      label: "Perempuan",
      backgroundColor: "#E91E63",
      data: [150, 230, 180], // Contoh data
    },
  ],
};

const barChartOptions = {
  responsive: true,
  plugins: {
    legend: {
      position: "top",
    },
    title: {
      display: false,
    },
  },
};

// Data untuk Pie Chart (Jenis Kelamin Siswa)
const genderPieChartData = {
  labels: ["Laki-laki", "Perempuan"],
  datasets: [
    {
      label: "Jenis Kelamin",
      backgroundColor: ["#4A90E2", "#E91E63"],
      data: [560, 480], // Contoh data
    },
  ],
};

// Data untuk Pie Chart (Status Kepegawaian Pendidik)
const employmentPieChartData = {
  labels: ["PNS", "Non PNS"],
  datasets: [
    {
      label: "Status Kepegawaian Pendidik",
      backgroundColor: ["#4A90E2", "#E91E63"],
      data: [70, 30], // Contoh data
    },
  ],
};

const pieChartOptions = {
  responsive: true,
  plugins: {
    legend: {
      position: "top",
    },
    title: {
      display: false,
    },
  },
};

</script>

<style scoped>

</style>