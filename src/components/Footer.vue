<script>
export default {
  name: "FooterComponent",
  data() {
    return {
      currentYear: new Date().getFullYear(),
      socialLinks: [
        {
          name: "GitHub",
          href: "https://github.com/afifahsalwa",
          icon: "github",
        },
        {
          name: "LinkedIn",
          href: "https://linkedin.com/in/afifahsalwa",
          icon: "linkedin",
        },
        {
          name: "Email",
          href: "mailto:afifahsalwa@email.com",
          icon: "email",
        },
      ],
      navLinks: [
        { label: "Home", href: "#hero" },
        { label: "About", href: "#about" },
        { label: "Contact", href: "#contact" },
      ],
    };
  },
};
</script>

<template>
  <footer class="bg-slate-900 text-slate-400 pt-14 pb-8 px-6 sm:px-8 lg:px-16">
    <div class="max-w-7xl mx-auto">
      <!-- Bagian Atas Footer -->
      <div
        class="grid grid-cols-1 md:grid-cols-3 gap-10 pb-10 border-b border-slate-800"
      >
        <!-- Kolom Brand -->
        <div class="space-y-4">
          <p
            class="text-xl font-bold tracking-wider bg-gradient-to-r from-emerald-400 to-teal-400 bg-clip-text text-transparent"
          >
            Afifah Salwa
          </p>
          <p class="text-sm leading-relaxed text-slate-500 max-w-xs">
            Frontend Developer & Designer yang bersemangat membangun antarmuka
            web yang indah dan fungsional.
          </p>
          <!-- Status Badge -->
          <div
            class="inline-flex items-center gap-2 px-3 py-1.5 rounded-full bg-emerald-950/60 border border-emerald-800/50 text-emerald-400 text-xs font-medium"
          >
            <span
              class="w-1.5 h-1.5 rounded-full bg-emerald-400 animate-ping"
            ></span>
            Open to work
          </div>
        </div>

        <!-- Kolom Navigasi -->
        <div>
          <h4
            class="text-xs font-bold uppercase tracking-widest text-slate-500 mb-5"
          >
            Navigasi
          </h4>
          <ul class="space-y-3">
            <li v-for="link in navLinks" :key="link.label">
              <a
                :href="link.href"
                class="text-sm text-slate-400 hover:text-emerald-400 transition-colors duration-200 flex items-center gap-2 group"
              >
                <span
                  class="w-0 h-px bg-emerald-400 group-hover:w-4 transition-all duration-300"
                ></span>
                {{ link.label }}
              </a>
            </li>
          </ul>
        </div>

        <!-- Kolom Tech Stack -->
        <div>
          <h4
            class="text-xs font-bold uppercase tracking-widest text-slate-500 mb-5"
          >
            Dibangun Dengan
          </h4>
          <div class="flex flex-wrap gap-2">
            <span
              v-for="tech in ['Vue.js', 'Tailwind CSS', 'JavaScript', 'Vite']"
              :key="tech"
              class="text-xs font-medium px-2.5 py-1 rounded-md bg-slate-800 text-slate-400 border border-slate-700"
            >
              {{ tech }}
            </span>
          </div>
        </div>
      </div>

      <!-- Bagian Bawah Footer: Copyright + Sosial -->
      <div
        class="pt-8 flex flex-col sm:flex-row items-center justify-between gap-4"
      >
        <p class="text-xs text-slate-600 text-center sm:text-left">
          © {{ currentYear }} Afifah Salwa. Dibuat dengan
          <span class="text-emerald-500">♥</span> menggunakan Vue.js & Tailwind
          CSS.
        </p>

        <!-- Social Icons -->
        <div class="flex items-center gap-3">
          <a
            v-for="social in socialLinks"
            :key="social.name"
            :href="social.href"
            :aria-label="social.name"
            target="_blank"
            rel="noopener noreferrer"
            class="w-9 h-9 rounded-lg bg-slate-800 border border-slate-700 hover:bg-emerald-600 hover:border-emerald-600 flex items-center justify-center text-slate-400 hover:text-white transition-all duration-200 hover:-translate-y-0.5"
          >
            <!-- GitHub -->
            <svg
              v-if="social.icon === 'github'"
              class="w-4 h-4"
              fill="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"
              />
            </svg>
            <!-- LinkedIn -->
            <svg
              v-else-if="social.icon === 'linkedin'"
              class="w-4 h-4"
              fill="currentColor"
              viewBox="0 0 24 24"
            >
              <path
                d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"
              />
            </svg>
            <!-- Email -->
            <svg
              v-else-if="social.icon === 'email'"
              class="w-4 h-4"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"
              />
            </svg>
          </a>
        </div>
      </div>
    </div>
  </footer>
</template>
