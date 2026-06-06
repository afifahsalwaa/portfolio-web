<script setup>
const currentYear = new Date().getFullYear();
const socialLinks = [
  {
    name: "GitHub",
    href: "https://github.com/afhslwa",
    icon: "github",
  },
  {
    name: "Instagram",
    href: "https://instagram.com/affhslwa",
    icon: "instagram",
  },
  {
    name: "Email",
    href: "mailto:afifahsalwa669@email.com",
    icon: "email",
  },
];
const navLinks = [
  { label: "Beranda", href: "#hero" },
  { label: "Tentang", href: "#about" },
  { label: "Pendidikan", href: "#education" },
  { label: "Kontak", href: "#contact" },
];
</script>

<template>
  <footer class="bg-slate-900 text-slate-400 pt-14 pb-8 px-6 sm:px-8 lg:px-16">
    <div class="max-w-7xl mx-auto">
      <!-- Bagian Atas Footer -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-10 pb-10 border-b border-slate-800">
        <!-- Kolom Brand -->
        <div class="space-y-4">
          <p
            class="text-xl font-bold tracking-wider bg-gradient-to-r from-emerald-400 to-teal-400 bg-clip-text text-transparent">
            Afifah Salwa
          </p>
          <p class="text-sm leading-relaxed text-slate-500 max-w-xs">
            Frontend Developer & Designer yang bersemangat membangun antarmuka
            web yang indah dan fungsional.
          </p>
          <!-- Status Badge -->
          <div
            class="inline-flex items-center gap-2 px-3 py-1.5 rounded-full bg-emerald-950/60 border border-emerald-800/50 text-emerald-400 text-xs font-medium">
            <span class="w-1.5 h-1.5 rounded-full bg-emerald-400 animate-ping"></span>
            Open to work
          </div>
        </div>

        <!-- Kolom Navigasi -->
        <div>
          <h4 class="text-xs font-bold uppercase tracking-widest text-slate-500 mb-5">
            Navigasi
          </h4>
          <ul class="space-y-3">
            <li v-for="link in navLinks" :key="link.label">
              <a :href="link.href"
                class="text-sm text-slate-400 hover:text-emerald-400 transition-colors duration-200 flex items-center gap-2 group">
                <span class="w-0 h-px bg-emerald-400 group-hover:w-4 transition-all duration-300"></span>
                {{ link.label }}
              </a>
            </li>
          </ul>
        </div>

        <!-- Kolom Tech Stack -->
        <div>
          <h4 class="text-xs font-bold uppercase tracking-widest text-slate-500 mb-5">
            Dibangun Dengan
          </h4>
          <div class="flex flex-wrap gap-2">
            <span v-for="tech in ['Vue.js', 'Tailwind CSS', 'JavaScript', 'Vite']" :key="tech"
              class="text-xs font-medium px-2.5 py-1 rounded-md bg-slate-800 text-slate-400 border border-slate-700">
              {{ tech }}
            </span>
          </div>
        </div>
      </div>

      <!-- Bagian Bawah Footer: Copyright + Sosial -->
      <div class="pt-8 flex flex-col sm:flex-row items-center justify-between gap-4">
        <p class="text-xs text-slate-600 text-center sm:text-left">
          © {{ currentYear }} Afifah Salwa. Dibuat dengan
          <span class="text-emerald-500">♥</span> menggunakan Vue.js & Tailwind
          CSS.
        </p>

        <!-- Social Icons -->
        <div class="flex items-center gap-3">
          <a v-for="social in socialLinks" :key="social.name" :href="social.href" :aria-label="social.name"
            target="_blank" rel="noopener noreferrer"
            class="w-9 h-9 rounded-lg bg-slate-800 border border-slate-700 hover:bg-emerald-600 hover:border-emerald-600 flex items-center justify-center text-slate-400 hover:text-white transition-all duration-200 hover:-translate-y-0.5">
            <!-- GitHub -->
            <svg v-if="social.icon === 'github'" class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
              <path
                d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12" />
            </svg>
            <!-- Instagram -->
            <svg v-else-if="social.icon === 'instagram'" class="w-4 h-4" fill="currentColor" viewBox="0 0 24 24">
              <path
                d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zM12 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z" />
            </svg>
            <!-- Email -->
            <svg v-else-if="social.icon === 'email'" class="w-4 h-4" fill="none" viewBox="0 0 24 24"
              stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
            </svg>
          </a>
        </div>
      </div>
    </div>
  </footer>
</template>
