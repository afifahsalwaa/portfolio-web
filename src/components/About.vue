<template>
  <section id="about" class="py-24 bg-slate-50/50 px-6 sm:px-8 lg:px-16 overflow-hidden scroll-mt-64 md:scroll-mt-0">
    <div class="max-w-7xl mx-auto">
      <!-- Judul Section -->
      <div class="text-center max-w-xl mx-auto mb-20">
        <h2 class="text-xs font-bold uppercase tracking-widest text-emerald-600 mb-2">
          Tentang Saya
        </h2>
        <p class="text-3xl sm:text-4xl font-extrabold text-slate-800 tracking-tight">
          Mengenal Lebih Dekat Perjalanan Saya
        </p>
        <div class="w-12 h-1 bg-emerald-500 mx-auto mt-4 rounded-full"></div>
      </div>

      <!-- Konten Utama: Grid 2 Kolom -->
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 lg:gap-20 items-center">
        <!-- Kolom Kiri: Cerita Singkat -->
        <div class="lg:col-span-6 space-y-8">
          <div class="space-y-4">
            <p class="text-slate-600 text-lg leading-relaxed">
              Halo! Nama saya Afifah Salwa. Saya memiliki hasrat mendalam dalam dunia pengembangan web dan desain
              visual. Saya percaya bahwa teknologi haruslah indah sekaligus fungsional.
            </p>
            <p class="text-slate-600 leading-relaxed underline decoration-emerald-200 decoration-4 underline-offset-4">
              Fokus utama saya saat ini adalah menguasai ekosistem JavaScript modern, terutama Vue.js dan Tailwind CSS,
              untuk membangun aplikasi web yang dinamis.
            </p>
          </div>

          <!-- Quick Info Grid -->
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-6 pt-4 border-t border-slate-200">
            <div class="flex items-center gap-4 group">
              <div
                class="w-12 h-12 rounded-2xl bg-white border border-slate-100 shadow-sm flex items-center justify-center text-emerald-600 group-hover:bg-emerald-600 group-hover:text-white transition-all duration-300">
                <svg class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path d="M12 14l9-5-9-5-9 5 9 5z" />
                  <path
                    d="M12 14l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14z" />
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                    d="M12 14l9-5-9-5-9 5 9 5zm0 0l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14zm-4 6v-7.5l4-2.222" />
                </svg>
              </div>
              <div>
                <p class="text-xs font-bold uppercase tracking-wider text-slate-400">Pendidikan</p>
                <p class="text-slate-700 font-semibold">S1 Teknik Informatika</p>
              </div>
            </div>
            <div class="flex items-center gap-4 group">
              <div
                class="w-12 h-12 rounded-2xl bg-white border border-slate-100 shadow-sm flex items-center justify-center text-emerald-600 group-hover:bg-emerald-600 group-hover:text-white transition-all duration-300">
                <svg class="w-5 h-5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                    d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                    d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
                </svg>
              </div>
              <div>
                <p class="text-xs font-bold uppercase tracking-wider text-slate-400">Lokasi</p>
                <p class="text-slate-700 font-semibold">Medan, Sumatera Utara</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Kolom Kanan: Soft Skills / Core Competencies -->
        <div class="lg:col-span-6 relative">
          <!-- Decorative Background Elements -->
          <div class="absolute -top-10 -right-10 w-64 h-64 bg-emerald-100/50 rounded-full blur-3xl pointer-events-none">
          </div>

          <div class="relative grid grid-cols-1 sm:grid-cols-2 gap-4">
            <div v-for="skill in softSkills" :key="skill.title"
              class="bg-white p-6 rounded-2xl border border-slate-100 shadow-sm hover:shadow-md hover:-translate-y-1 transition-all duration-300">
              <div class="w-10 h-10 rounded-xl bg-emerald-50 text-emerald-600 flex items-center justify-center mb-4">
                <span class="text-xl">{{ skill.icon }}</span>
              </div>
              <h4 class="font-bold text-slate-800 mb-1">{{ skill.title }}</h4>
              <p class="text-xs text-slate-500 leading-relaxed">{{ skill.desc }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const softSkills = [
  {
    title: 'Problem Solving',
    icon: '💡',
    desc: 'Mampu menganalisis masalah kompleks dan menemukan solusi efisien.'
  },
  {
    title: 'Responsive Design',
    icon: '🎨',
    desc: 'Memastikan tampilan website optimal di semua ukuran layar.'
  },
  {
    title: 'Kerja Sama Tim',
    icon: '🤝',
    desc: 'Aktif berkomunikasi dan berkontribusi dalam berbagai proyek.'
  },
  {
    title: 'Detail Oriented',
    icon: '🔍',
    desc: 'Sangat memperhatikan detail estetika dan fungsionalitas kode.'
  }
];
</script>
