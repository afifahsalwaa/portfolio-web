<script setup>
import { ref, reactive } from "vue";

const form = reactive({
  name: "",
  email: "",
  message: "",
});

const isSubmitting = ref(false);
const submitStatus = ref(null); // 'success' | 'error' | null

const contactInfo = [
  {
    icon: "email",
    label: "Email",
    value: "afifahsalwa669@gmail.com",
    href: "mailto:afifahsalwa669@gmail.com",
  },
  {
    icon: "location",
    label: "Lokasi",
    value: "Medan, Sumatera Utara",
    href: null,
  },
  {
    icon: "instagram",
    label: "Instagram",
    value: "@affhslwa",
    href: "https://instagram.com/affhslwa",
  },
  {
    icon: "github",
    label: "GitHub",
    value: "afifahsalwaa",
    href: "https://github.com/afifahsalwaa",
  },
];

const handleSubmit = () => {
  if (!form.name || !form.email || !form.message) return;

  const recipient = "afifahsalwa669@gmail.com";
  const subject = encodeURIComponent(`Pesan Kontak Portfolio dari ${form.name}`);
  const body = encodeURIComponent(
    `Halo Afifah,\n\nNama: ${form.name}\nEmail: ${form.email}\n\nPesan:\n${form.message}`
  );

  // Membuka Gmail bursa pesan baru di tab baru
  const gmailUrl = `https://mail.google.com/mail/?view=cm&fs=1&to=${recipient}&su=${subject}&body=${body}`;
  window.open(gmailUrl, "_blank");

  // Reset form
  form.name = "";
  form.email = "";
  form.message = "";

  submitStatus.value = "success";
  setTimeout(() => {
    submitStatus.value = null;
  }, 5000);
};
</script>

<template>
  <section id="contact" class="py-24 bg-white px-6 sm:px-8 lg:px-16 overflow-hidden scroll-mt-64 md:scroll-mt-0">
    <!-- Dekoratif latar belakang -->
    <div class="absolute left-0 w-72 h-72 bg-emerald-100/50 rounded-full blur-3xl -translate-x-1/2 pointer-events-none">
    </div>

    <div class="max-w-7xl mx-auto relative">
      <!-- Judul Section -->
      <div class="text-center max-w-xl mx-auto mb-16">
        <h2 class="text-xs font-bold uppercase tracking-widest text-emerald-600 mb-2">
          Kontak
        </h2>
        <p class="text-3xl sm:text-4xl font-extrabold text-slate-800 tracking-tight">
          Mari Berkolaborasi
        </p>
        <p class="text-slate-500 mt-4 leading-relaxed">
          Punya proyek menarik atau sekadar ingin berdiskusi? Saya terbuka untuk
          peluang baru — kirim pesan dan saya akan segera membalas!
        </p>
        <div class="w-12 h-1 bg-emerald-500 mx-auto mt-4 rounded-full"></div>
      </div>

      <!-- Grid: Info Kontak + Form -->
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 items-start">
        <!-- Kolom Kiri: Info Kontak -->
        <div class="lg:col-span-5 space-y-6">
          <div class="bg-slate-50 rounded-2xl p-8 border border-slate-100">
            <h3 class="text-lg font-bold text-slate-800 mb-6">
              Informasi Kontak
            </h3>
            <ul class="space-y-5">
              <li v-for="item in contactInfo" :key="item.label" class="flex items-start gap-4">
                <!-- Icon -->
                <div
                  class="flex-shrink-0 w-10 h-10 rounded-xl bg-emerald-50 border border-emerald-100 flex items-center justify-center">
                  <!-- Email -->
                  <svg v-if="item.icon === 'email'" class="w-4 h-4 text-emerald-600" fill="none" viewBox="0 0 24 24"
                    stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                      d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                  </svg>
                  <!-- Location -->
                  <svg v-else-if="item.icon === 'location'" class="w-4 h-4 text-emerald-600" fill="none"
                    viewBox="0 0 24 24" stroke="currentColor">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                      d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z" />
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                      d="M15 11a3 3 0 11-6 0 3 3 0 016 0z" />
                  </svg>
                  <!-- LinkedIn -->
                  <svg v-else-if="item.icon === 'instagram'" class="w-4 h-4 text-emerald-600" fill="currentColor"
                    viewBox="0 0 24 24">
                    <path
                      d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zM12 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z" />
                  </svg>
                  <!-- GitHub -->
                  <svg v-else-if="item.icon === 'github'" class="w-4 h-4 text-emerald-600" fill="currentColor"
                    viewBox="0 0 24 24">
                    <path
                      d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12" />
                  </svg>
                </div>
                <div>
                  <p class="text-xs font-bold uppercase tracking-wider text-slate-400">
                    {{ item.label }}
                  </p>
                  <a v-if="item.href" :href="item.href" target="_blank" rel="noopener noreferrer"
                    class="text-slate-700 font-medium text-sm hover:text-emerald-600 transition-colors duration-200">{{
                      item.value }}</a>
                  <p v-else class="text-slate-700 font-medium text-sm">
                    {{ item.value }}
                  </p>
                </div>
              </li>
            </ul>
          </div>

          <!-- Status Availability Badge -->
          <div class="flex items-center gap-3 px-5 py-4 bg-emerald-50 border border-emerald-100 rounded-xl">
            <span class="w-2.5 h-2.5 rounded-full bg-emerald-500 animate-ping flex-shrink-0"></span>
            <p class="text-sm text-emerald-700 font-medium">
              Saat ini tersedia untuk proyek freelance & full-time.
            </p>
          </div>
        </div>

        <!-- Kolom Kanan: Form -->
        <div class="lg:col-span-7">
          <div class="bg-white rounded-2xl border border-slate-100 shadow-sm p-8">
            <h3 class="text-lg font-bold text-slate-800 mb-6">Kirim Pesan</h3>

            <!-- Success Alert -->
            <transition name="fade">
              <div v-if="submitStatus === 'success'"
                class="mb-6 flex items-center gap-3 px-4 py-3.5 bg-emerald-50 border border-emerald-200 text-emerald-700 rounded-xl text-sm font-medium">
                <svg class="w-5 h-5 flex-shrink-0" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                    d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z" />
                </svg>
                Pesan berhasil dikirim! Saya akan segera membalas. 🎉
              </div>
            </transition>

            <form @submit.prevent="handleSubmit" class="space-y-5">
              <!-- Name & Email -->
              <div class="grid grid-cols-1 sm:grid-cols-2 gap-5">
                <div>
                  <label for="name" class="block text-xs font-bold uppercase tracking-wider text-slate-500 mb-2">Nama
                    Lengkap</label>
                  <input id="name" v-model="form.name" type="text" placeholder="Afifah Salwa" required
                    class="w-full px-4 py-3 rounded-xl border border-slate-200 bg-slate-50 text-slate-800 text-sm placeholder-slate-400 focus:outline-none focus:ring-2 focus:ring-emerald-400 focus:border-transparent focus:bg-white transition-all duration-200" />
                </div>
                <div>
                  <label for="email" class="block text-xs font-bold uppercase tracking-wider text-slate-500 mb-2">Alamat
                    Email</label>
                  <input id="email" v-model="form.email" type="email" placeholder="123456@gmail.com" required
                    class="w-full px-4 py-3 rounded-xl border border-slate-200 bg-slate-50 text-slate-800 text-sm placeholder-slate-400 focus:outline-none focus:ring-2 focus:ring-emerald-400 focus:border-transparent focus:bg-white transition-all duration-200" />
                </div>
              </div>

              <!-- Message -->
              <div>
                <label for="message"
                  class="block text-xs font-bold uppercase tracking-wider text-slate-500 mb-2">Pesan</label>
                <textarea id="message" v-model="form.message" rows="5"
                  placeholder="Halo Afifah, saya ingin berdiskusi tentang..." required
                  class="w-full px-4 py-3 rounded-xl border border-slate-200 bg-slate-50 text-slate-800 text-sm placeholder-slate-400 focus:outline-none focus:ring-2 focus:ring-emerald-400 focus:border-transparent focus:bg-white transition-all duration-200 resize-none"></textarea>
              </div>

              <!-- Submit Button -->
              <button type="submit" :disabled="isSubmitting"
                class="w-full px-8 py-3.5 bg-emerald-600 hover:bg-emerald-700 disabled:bg-emerald-400 disabled:cursor-not-allowed text-white font-semibold rounded-xl shadow-lg shadow-emerald-600/20 hover:shadow-emerald-600/30 hover:-translate-y-0.5 disabled:translate-y-0 transition-all duration-200 flex items-center justify-center gap-2">
                <svg v-if="isSubmitting" class="w-4 h-4 animate-spin" fill="none" viewBox="0 0 24 24">
                  <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
                  <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4z"></path>
                </svg>
                <span>{{ isSubmitting ? "Mengirim..." : "Kirim Pesan" }}</span>
                <svg v-if="!isSubmitting" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
                    d="M12 19l9 2-9-18-9 18 9-2zm0 0v-8" />
                </svg>
              </button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition:
    opacity 0.4s ease,
    transform 0.4s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
  transform: translateY(-8px);
}
</style>
