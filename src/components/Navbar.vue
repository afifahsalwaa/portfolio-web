<script>
export default {
  name: "NavbarComponent",
  data() {
    return {
      // State untuk melacak status menu hamburger (terbuka/tertutup)
      isOpen: false,
    };
  },
};
</script>

<template>
  <nav
    class="bg-white/80 backdrop-blur-md sticky top-0 z-50 border-b border-emerald-100 shadow-sm transition-all duration-300"
  >
    <div class="max-w-7xl mx-auto px-6 sm:px-8 lg:px-16">
      <div class="flex justify-between h-16 items-center">
        <!-- Logo / Nama -->
        <div class="flex-shrink-0">
          <p
            class="text-xl font-bold tracking-wider bg-gradient-to-r from-emerald-600 to-teal-500 bg-clip-text text-transparent hover:scale-105 transition-transform duration-200 cursor-pointer"
          >
            Afifah Salwa
          </p>
        </div>

        <!-- Desktop Navigation Menu (Sembunyi di HP, Muncul di Layar Medium ke Atas) -->
        <ul
          class="hidden md:flex items-center gap-8 font-medium tracking-wide text-slate-600"
        >
          <li>
            <a
              href="#"
              class="hover:text-emerald-500 transition-colors duration-200 relative after:content-[''] after:absolute after:left-0 after:bottom-[-4px] after:w-0 after:h-[2px] after:bg-emerald-500 hover:after:w-full after:transition-all after:duration-300"
              >Home</a
            >
          </li>
          <li>
            <a
              href="#"
              class="hover:text-emerald-500 transition-colors duration-200 relative after:content-[''] after:absolute after:left-0 after:bottom-[-4px] after:w-0 after:h-[2px] after:bg-emerald-500 hover:after:w-full after:transition-all after:duration-300"
              >About</a
            >
          </li>
          <li>
            <a
              href="#"
              class="hover:text-emerald-500 transition-colors duration-200 relative after:content-[''] after:absolute after:left-0 after:bottom-[-4px] after:w-0 after:h-[2px] after:bg-emerald-500 hover:after:w-full after:transition-all after:duration-300"
              >Contact</a
            >
          </li>
        </ul>

        <!-- Hamburger Button (Muncul HANYA di HP/Tablet kecil) -->
        <div class="flex md:hidden">
          <button
            @click="isOpen = !isOpen"
            type="button"
            class="text-slate-600 hover:text-emerald-500 hover:bg-emerald-50 p-2 rounded-lg focus:outline-none transition-colors"
            aria-label="Toggle menu"
          >
            <!-- Icon Hamburger (X saat terbuka, Garis 3 saat tertutup) -->
            <svg
              class="h-6 w-6"
              fill="none"
              viewBox="0 0 24 24"
              stroke="currentColor"
            >
              <path
                v-if="!isOpen"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 12h16M4 18h16"
              />
              <path
                v-else
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Navigation Menu (Muncul dengan animasi slide down saat Hamburger di-klik) -->
    <div
      v-show="isOpen"
      class="md:hidden border-t border-emerald-50 bg-white/95 backdrop-blur-md dynamic-mobile-menu"
    >
      <ul
        class="px-6 pt-3 pb-6 space-y-3 font-medium tracking-wide text-slate-600"
      >
        <li>
          <a
            href="#"
            class="block px-4 py-2.5 rounded-lg hover:bg-emerald-50 hover:text-emerald-600 transition-all duration-200"
            >Home</a
          >
        </li>
        <li>
          <a
            href="#"
            class="block px-4 py-2.5 rounded-lg hover:bg-emerald-50 hover:text-emerald-600 transition-all duration-200"
            >About</a
          >
        </li>
        <li>
          <a
            href="#"
            class="block px-4 py-2.5 rounded-lg hover:bg-emerald-50 hover:text-emerald-600 transition-all duration-200"
            >Contact</a
          >
        </li>
      </ul>
    </div>
  </nav>
</template>
