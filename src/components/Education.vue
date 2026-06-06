<script setup>
const educations = [
  {
    id: 1,
    period: "2025 – Sekarang",
    degree: "S1 Teknik Informatika",
    institution: "Universitas Satya Terra Bhinneka",
    location: "Medan, Sumatera Utara",
    description:
      "Berfokus pada pengembangan perangkat lunak, algoritma, dan desain antarmuka pengguna. Aktif di organisasi Interfaith Islamic Student Association.",
    highlights: ["Sekertaris Interfaith Islamic Student Association"],
    status: "active",
    icon: "university",
  },
  {
    id: 2,
    period: "2022 – 2025",
    degree: "Rekayasa Perangkat Lunak",
    institution: "SMK Negeri 2 Tebing Tinggi",
    location: "Tebing Tinggi, Sumatera Utara",
    description:
      "Mulai mengenal dunia pemrograman secara otodidak melalui kursus online dan proyek-proyek kecil.",
    highlights: [
      "Masuk peringkat 10 besar lebih dari 3 kali",
      "Anggota Rohis",
      "Mengikuti Kursus Komputer",
    ],
    status: "done",
    icon: "school",
  },
];
const certifications = [
  {
    name: "Intoduction to Python",
    issuer: "SoloLearn",
    year: "2026",
    color: "emerald",
  },
  {
    name: "SDGs 101",
    issuer: "SDG Academy Indonesia",
    year: "2026",
    color: "emerald",
  },
];
</script>

<template>
  <section id="education" class="py-24 bg-white px-6 sm:px-8 lg:px-16 overflow-hidden scroll-mt-64 md:scroll-mt-0">
    <div class="max-w-7xl mx-auto">
      <!-- Header Section -->
      <div class="text-center max-w-xl mx-auto mb-16">
        <h2 class="text-xs font-bold uppercase tracking-widest text-emerald-600 mb-2">
          Riwayat Pendidikan
        </h2>
        <p class="text-3xl sm:text-4xl font-extrabold text-slate-800 tracking-tight">
          Perjalanan Belajar Saya
        </p>
        <p class="text-slate-500 mt-4 leading-relaxed">
          Fondasi akademis yang membentuk cara berpikir dan kemampuan teknis
          saya sebagai developer.
        </p>
        <div class="w-12 h-1 bg-emerald-500 mx-auto mt-4 rounded-full"></div>
      </div>

      <div class="grid grid-cols-1 lg:grid-cols-12 gap-16 items-start">
        <!-- Kolom Kiri: Timeline -->
        <div class="lg:col-span-7">
          <div class="relative">
            <!-- Garis vertikal timeline -->
            <div
              class="absolute left-5 top-0 bottom-0 w-px bg-gradient-to-b from-emerald-400 via-emerald-200 to-transparent">
            </div>

            <div class="space-y-10">
              <div v-for="(edu, index) in educations" :key="edu.id" class="relative pl-14 group">
                <!-- Dot Timeline -->
                <div :class="[
                  'absolute left-0 top-1 w-10 h-10 rounded-xl flex items-center justify-center border-2 transition-all duration-300 group-hover:scale-110',
                  edu.status === 'active'
                    ? 'bg-emerald-500 border-emerald-400 shadow-md shadow-emerald-500/30'
                    : 'bg-white border-emerald-200 group-hover:border-emerald-400',
                ]">
                  <!-- University Icon -->
                  <svg v-if="edu.icon === 'university'" :class="[
                    'w-4 h-4',
                    edu.status === 'active'
                      ? 'text-white'
                      : 'text-emerald-500',
                  ]" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 14l9-5-9-5-9 5 9 5z" />
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                      d="M12 14l6.16-3.422a12.083 12.083 0 01.665 6.479A11.952 11.952 0 0012 20.055a11.952 11.952 0 00-6.824-2.998 12.078 12.078 0 01.665-6.479L12 14z" />
                  </svg>
                  <!-- School Icon -->
                  <svg v-else :class="[
                    'w-4 h-4',
                    edu.status === 'active'
                      ? 'text-white'
                      : 'text-emerald-500',
                  ]" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                      d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4" />
                  </svg>
                </div>

                <!-- Card Konten -->
                <div :class="[
                  'bg-white rounded-2xl border p-6 transition-all duration-300 group-hover:shadow-md group-hover:-translate-y-0.5',
                  edu.status === 'active'
                    ? 'border-emerald-200 shadow-sm shadow-emerald-100'
                    : 'border-slate-100 shadow-sm',
                ]">
                  <!-- Header Card -->
                  <div class="flex flex-wrap items-start justify-between gap-2 mb-3">
                    <div>
                      <h3 class="text-lg font-extrabold text-slate-800 leading-tight">
                        {{ edu.degree }}
                      </h3>
                      <p class="text-emerald-600 font-semibold text-sm mt-0.5">
                        {{ edu.institution }}
                      </p>
                    </div>
                    <div class="flex flex-col items-end gap-1.5">
                      <span class="text-xs font-bold px-2.5 py-1 rounded-md bg-slate-100 text-slate-500">
                        {{ edu.period }}
                      </span>
                      <span v-if="edu.status === 'active'"
                        class="inline-flex items-center gap-1.5 text-xs font-bold px-2.5 py-1 rounded-md bg-emerald-50 text-emerald-600 border border-emerald-100">
                        <span class="w-1.5 h-1.5 rounded-full bg-emerald-500 animate-ping"></span>
                        Sedang Berjalan
                      </span>
                      <span v-else
                        class="text-xs font-bold px-2.5 py-1 rounded-md bg-slate-50 text-slate-400 border border-slate-100">
                        ✓ Selesai
                      </span>
                    </div>
                  </div>

                  <!-- Lokasi -->
                  <div class="flex items-center gap-1.5 text-slate-400 text-xs mb-3">
                    <svg class="w-3.5 h-3.5" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                        d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                        d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
                    </svg>
                    {{ edu.location }}
                  </div>

                  <!-- Deskripsi -->
                  <p class="text-slate-500 text-sm leading-relaxed mb-4">
                    {{ edu.description }}
                  </p>

                  <!-- Highlights/Pencapaian -->
                  <div class="flex flex-wrap gap-2">
                    <span v-for="h in edu.highlights" :key="h"
                      class="text-xs font-medium px-2.5 py-1 rounded-lg bg-emerald-50 text-emerald-700 border border-emerald-100">
                      🏅 {{ h }}
                    </span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Kolom Kanan: Sertifikasi -->
        <div class="lg:col-span-5 space-y-6">
          <div class="bg-slate-50 rounded-2xl p-8 border border-slate-100">
            <div class="flex items-center gap-3 mb-6">
              <div class="w-9 h-9 rounded-xl bg-emerald-100 flex items-center justify-center">
                <svg class="w-4 h-4 text-emerald-600" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                    d="M9 12l2 2 4-4M7.835 4.697a3.42 3.42 0 001.946-.806 3.42 3.42 0 014.438 0 3.42 3.42 0 001.946.806 3.42 3.42 0 013.138 3.138 3.42 3.42 0 00.806 1.946 3.42 3.42 0 010 4.438 3.42 3.42 0 00-.806 1.946 3.42 3.42 0 01-3.138 3.138 3.42 3.42 0 00-1.946.806 3.42 3.42 0 01-4.438 0 3.42 3.42 0 00-1.946-.806 3.42 3.42 0 01-3.138-3.138 3.42 3.42 0 00-.806-1.946 3.42 3.42 0 010-4.438 3.42 3.42 0 00.806-1.946 3.42 3.42 0 013.138-3.138z" />
                </svg>
              </div>
              <h4 class="text-lg font-bold text-slate-800">Sertifikasi</h4>
            </div>

            <div class="space-y-3">
              <div v-for="cert in certifications" :key="cert.name"
                class="flex items-center gap-4 bg-white p-4 rounded-xl border border-slate-100 hover:border-emerald-200 hover:shadow-sm transition-all duration-200 group">
                <div
                  class="w-8 h-8 rounded-lg bg-emerald-50 flex items-center justify-center flex-shrink-0 group-hover:bg-emerald-100 transition-colors duration-200">
                  <svg class="w-4 h-4 text-emerald-500" fill="currentColor" viewBox="0 0 20 20">
                    <path fill-rule="evenodd"
                      d="M6.267 3.455a3.066 3.066 0 001.745-.723 3.066 3.066 0 013.976 0 3.066 3.066 0 001.745.723 3.066 3.066 0 012.812 2.812c.051.643.304 1.254.723 1.745a3.066 3.066 0 010 3.976 3.066 3.066 0 00-.723 1.745 3.066 3.066 0 01-2.812 2.812 3.066 3.066 0 00-1.745.723 3.066 3.066 0 01-3.976 0 3.066 3.066 0 00-1.745-.723 3.066 3.066 0 01-2.812-2.812 3.066 3.066 0 00-.723-1.745 3.066 3.066 0 010-3.976 3.066 3.066 0 00.723-1.745 3.066 3.066 0 012.812-2.812zm7.44 5.252a1 1 0 00-1.414-1.414L9 10.586 7.707 9.293a1 1 0 00-1.414 1.414l2 2a1 1 0 001.414 0l4-4z"
                      clip-rule="evenodd" />
                  </svg>
                </div>
                <div class="flex-1 min-w-0">
                  <p class="text-sm font-semibold text-slate-700 truncate">
                    {{ cert.name }}
                  </p>
                  <p class="text-xs text-slate-400">{{ cert.issuer }}</p>
                </div>
                <span class="text-xs font-bold text-emerald-600 bg-emerald-50 px-2 py-0.5 rounded-md flex-shrink-0">
                  {{ cert.year }}
                </span>
              </div>
            </div>
          </div>

          <!-- Quote / Filosofi Belajar -->
          <div class="relative bg-gradient-to-br from-emerald-600 to-teal-500 rounded-2xl p-6 overflow-hidden">
            <div class="absolute -top-4 -right-4 w-24 h-24 bg-white/10 rounded-full"></div>
            <div class="absolute -bottom-6 -left-6 w-32 h-32 bg-white/5 rounded-full"></div>
            <div class="relative z-10">
              <svg class="w-7 h-7 text-white/60 mb-3" fill="currentColor" viewBox="0 0 24 24">
                <path
                  d="M14.017 21v-7.391c0-5.704 3.731-9.57 8.983-10.609l.995 2.151c-2.432.917-3.995 3.638-3.995 5.849h4v10h-9.983zm-14.017 0v-7.391c0-5.704 3.748-9.57 9-10.609l.996 2.151c-2.433.917-3.996 3.638-3.996 5.849h3.983v10h-9.983z" />
              </svg>
              <p class="text-white font-semibold leading-relaxed text-sm">
                "Belajar bukan tentang seberapa banyak yang kita tahu, tapi
                seberapa jauh kita bisa tumbuh."
              </p>
              <p class="text-white/60 text-xs mt-3 font-medium">
                — Afifah Salwa
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
