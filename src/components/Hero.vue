<script setup>
import afifah from "./../assets/afifah.jpeg";
</script>

<template>
  <section id="hero"
    class="scroll-pt-40 relative min-h-[calc(100vh-4rem)] flex items-center justify-center bg-linear-to-b from-emerald-50/30 via-white to-white overflow-hidden py-20 px-6 sm:px-8 lg:px-16 scroll-mt-80 md:scroll-mt-0">
    <!-- Elemen Dekoratif Latar Belakang (Abstract Blobs) -->
    <div
      class="absolute top-1/4 left-10 w-72 h-72 bg-emerald-200/40 rounded-full blur-3xl mix-blend-multiply filter animate-pulse">
    </div>
    <div
      class="absolute bottom-1/4 right-10 w-96 h-96 bg-teal-200/30 rounded-full blur-3xl mix-blend-multiply filter animate-pulse"
      style="animation-delay: 2s"></div>

    <div class="max-w-7xl mx-auto grid grid-cols-1 lg:grid-cols-12 gap-12 items-center relative z-10">
      <!-- Teks Utama (Kiri di Desktop) -->
      <div class="lg:col-span-7 text-center lg:text-left space-y-6">
        <h1 class="text-4xl sm:text-5xl lg:text-6xl font-extrabold text-slate-800 tracking-tight leading-tight">
          Hai, Saya
          <span class="bg-linear-to-r from-emerald-600 to-teal-500 bg-clip-text text-transparent">Afifah Salwa</span>
          <br />
          <span class="text-3xl sm:text-4xl lg:text-5xl text-slate-700 font-bold block mt-2">
            Frontend Developer & Designer
          </span>
        </h1>

        <p class="text-slate-600 text-base sm:text-lg max-w-xl mx-auto lg:mx-0 leading-relaxed">
          Seorang mahasiswa jurusan Teknik Informatika yang memiliki ketertarikan besar dalam pengembangan web dan
          desain grafis. Saya aktif dalam berbagai kegiatan organisasi dan kepanitiaan yang mengasah kemampuan
          kepemimpinan, kerja sama tim, serta manajemen proyek. Dengan semangat belajar yang tinggi dan keinginan untuk
          terus berkembang, saya siap menghadapi tantangan baru di dunia profesional.
        </p>

        <!-- Tombol Aksi (CTA Buttons) -->
        <div class="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start pt-4">
          <a href="#projects"
            class="px-8 py-3.5 bg-emerald-600 hover:bg-emerald-700 text-white font-semibold rounded-xl shadow-lg shadow-emerald-600/20 hover:shadow-emerald-600/30 hover:-translate-y-0.5 transition-all duration-200 text-center">
            Lihat CV Saya
          </a>
          <a href="#contact"
            class="px-8 py-3.5 bg-white hover:bg-slate-50 text-slate-700 font-semibold rounded-xl border border-slate-200 shadow-sm hover:-translate-y-0.5 transition-all duration-200 text-center">
            Hubungi Saya
          </a>
        </div>

      </div>

      <!-- Area Gambar/Ilustrasi (Kanan di Desktop) -->
      <div class="lg:col-span-5 flex justify-center items-center">
        <div class="relative w-64 h-64 sm:w-80 sm:h-80 lg:w-96 lg:h-96">
          <!-- Bingkai Dekoratif Belakang Gambar -->
          <div
            class="absolute inset-0 bg-linear-to-tr from-emerald-500 to-teal-400 rounded-2xl rotate-6 scale-95 opacity-20 animate-pulse">
          </div>
          <div class="absolute inset-0 bg-emerald-100 rounded-3xl -rotate-3 scale-100"></div>

          <!-- Box Utama Tempat Foto Profil / Ilustrasi -->
          <div
            class="absolute inset-0 bg-slate-100 rounded-2xl border-2 border-white shadow-xl overflow-hidden flex items-center justify-center">
            <img :src="afifah" alt="Afifah Salwa"
              class="block text-slate-400 object-cover text-sm italic font-medium p-4 text-center" />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
