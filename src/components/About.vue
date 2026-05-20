<template>
  <section
    id="about"
    class="py-24 bg-slate-50/50 px-6 sm:px-8 lg:px-16 overflow-hidden"
  >
    <div class="max-w-7xl mx-auto">
      <!-- Judul Section -->
      <div class="text-center max-w-xl mx-auto mb-16">
        <h2
          class="text-xs font-bold uppercase tracking-widest text-emerald-600 mb-2"
        >
          Tentang Saya
        </h2>
        <p
          class="text-3xl sm:text-4xl font-extrabold text-slate-800 tracking-tight"
        >
          Mengenal Lebih Dekat Perjalanan Saya
        </p>
        <div class="w-12 h-1 bg-emerald-500 mx-auto mt-4 rounded-full"></div>
      </div>

      <!-- Konten Utama: Grid 2 Kolom -->
      <div
        class="grid grid-cols-1 lg:grid-cols-12 gap-12 lg:gap-20 items-start"
      >
        <!-- Kolom Kiri: Cerita Singkat & Statistik -->
        <div class="lg:col-span-6 space-y-6">
          <h3 class="text-2xl font-bold text-slate-800">
            Saya seorang Developer yang menjembatani antara
            <span class="text-emerald-600">Desain</span> dan
            <span class="text-teal-500">Kode</span>.
          </h3>

          <p class="text-slate-600 leading-relaxed">
            Halo! Nama saya Afifah Salwa. Saya memiliki hasrat mendalam dalam
            dunia pengembangan web, khususnya di bagian *Frontend Development*.
            Saya suka merapikan baris kode demi menciptakan halaman web yang
            tidak hanya estetik saat dilihat, tetapi juga terasa responsif,
            cepat, dan mudah digunakan oleh siapa saja.
          </p>

          <p class="text-slate-600 leading-relaxed">
            Fokus utama saya saat ini adalah menguasai ekosistem JavaScript
            modern, terutama Vue.js dan Tailwind CSS, untuk membangun aplikasi
            web yang dinamis dan terstruktur dengan baik.
          </p>

          <!-- Statistik Ringkas / Pencapaian -->
          <div class="grid grid-cols-3 gap-4 pt-6 border-t border-slate-200">
            <div>
              <p class="text-3xl font-extrabold text-emerald-600">1+</p>
              <p
                class="text-xs font-medium uppercase text-slate-500 tracking-wider mt-1"
              >
                Tahun Pengalaman
              </p>
            </div>
            <div>
              <p class="text-3xl font-extrabold text-emerald-600">15+</p>
              <p
                class="text-xs font-medium uppercase text-slate-500 tracking-wider mt-1"
              >
                Project Selesai
              </p>
            </div>
            <div>
              <p class="text-3xl font-extrabold text-emerald-600">5+</p>
              <p
                class="text-xs font-medium uppercase text-slate-500 tracking-wider mt-1"
              >
                Klien Puas
              </p>
            </div>
          </div>
        </div>

        <!-- Kolom Kanan: Skill Bars & Core Competencies -->
        <div
          class="lg:col-span-6 bg-white p-8 rounded-2xl shadow-sm border border-slate-100 space-y-6"
        >
          <h4
            class="text-lg font-bold text-slate-800 border-b border-slate-100 pb-3"
          >
            Keahlian Teknis
          </h4>

          <!-- Loop Skill Bars menggunakan Vue data -->
          <div class="space-y-5">
            <div v-for="skill in skills" :key="skill.name">
              <div class="flex justify-between items-center mb-1.5">
                <span class="text-sm font-semibold text-slate-700">{{
                  skill.name
                }}</span>
                <span
                  class="text-xs font-bold text-emerald-600 bg-emerald-50 px-2 py-0.5 rounded-md"
                >
                  {{ skill.level }}%
                </span>
              </div>
              <!-- Track Bar -->
              <div class="w-full h-2 bg-slate-100 rounded-full overflow-hidden">
                <!-- Progress Bar -->
                <div
                  class="h-full bg-linear-to-r from-emerald-500 to-teal-400 rounded-full transition-all duration-1000 ease-out"
                  :style="{ width: skill.level + '%' }"
                ></div>
              </div>
            </div>
          </div>

          <!-- Tambahan Soft Skills / Nilai Plus -->
          <div class="pt-4">
            <p
              class="text-xs font-bold uppercase tracking-wider text-slate-400 mb-3"
            >
              Nilai Tambah & Pola Pikir
            </p>
            <div class="flex flex-wrap gap-2">
              <span
                class="text-xs font-medium bg-slate-50 text-slate-600 px-3 py-1.5 rounded-lg border border-slate-100"
                >💡 Problem Solving</span
              >
              <span
                class="text-xs font-medium bg-slate-50 text-slate-600 px-3 py-1.5 rounded-lg border border-slate-100"
                >🎨 Responsive Design Mindset</span
              >
              <span
                class="text-xs font-medium bg-slate-50 text-slate-600 px-3 py-1.5 rounded-lg border border-slate-100"
                >🤝 Kolaboratif</span
              >
              <span
                class="text-xs font-medium bg-slate-50 text-slate-600 px-3 py-1.5 rounded-lg border border-slate-100"
                >🔍 Detail Oriented</span
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "AboutComponent",
  data() {
    return {
      // Data keahlian yang bisa kamu ubah persentasenya sesuai kemampuanmu
      skills: [
        { name: "Vue.js / JavaScript (ES6+)", level: 85 },
        { name: "HTML5 & CSS3 / Semantic Web", level: 90 },
        { name: "Tailwind CSS / Responsive Design", level: 95 },
        { name: "Git & GitHub Version Control", level: 80 },
        { name: "UI/UX Design & Figma Layouts", level: 75 },
      ],
    };
  },
};
</script>
