<script>
export default {
  name: "NavbarComponent",
  data() {
    return {
      isOpen: false,
      isScrolled: false,
      activeSection: "hero",
      navLinks: [
        { label: "Home", href: "#hero", section: "hero" },
        { label: "About", href: "#about", section: "about" },
        { label: "Education", href: "#education", section: "education" },
        { label: "Contact", href: "#contact", section: "contact" },
      ],
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
    this.setupIntersectionObserver();
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
    if (this.observer) this.observer.disconnect();
  },
  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY > 20;
    },
    setupIntersectionObserver() {
      const sections = ["hero", "about", "education", "contact"];
      this.observer = new IntersectionObserver(
        (entries) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting) {
              this.activeSection = entry.target.id;
            }
          });
        },
        { threshold: 0.4 },
      );
      sections.forEach((id) => {
        const el = document.getElementById(id);
        if (el) this.observer.observe(el);
      });
    },
    closeMenu() {
      this.isOpen = false;
    },
  },
};
</script>

<template>
  <nav
    :class="[
      'sticky top-0 z-50 transition-all duration-300',
      isScrolled
        ? 'bg-white/95 backdrop-blur-md shadow-md border-b border-emerald-100'
        : 'bg-white/80 backdrop-blur-md border-b border-emerald-100 shadow-sm',
    ]"
  >
    <div class="max-w-7xl mx-auto px-6 sm:px-8 lg:px-16">
      <div class="flex justify-between h-16 items-center">
        <!-- Logo -->
        <a href="#hero" class="shrink-0 group">
          <p
            class="text-xl font-bold tracking-wider bg-linear-to-r from-emerald-600 to-teal-500 bg-clip-text text-transparent group-hover:scale-105 transition-transform duration-200"
          >
            Afifah Salwa
          </p>
        </a>

        <!-- Desktop Nav -->
        <ul class="hidden md:flex items-center gap-1 font-medium tracking-wide">
          <li v-for="link in navLinks" :key="link.section">
            <a
              :href="link.href"
              :class="[
                'relative px-4 py-2 rounded-lg text-sm transition-all duration-200',
                activeSection === link.section
                  ? 'text-emerald-600 bg-emerald-50'
                  : 'text-slate-600 hover:text-emerald-600 hover:bg-emerald-50/60',
              ]"
            >
              {{ link.label }}
              <!-- Active indicator dot -->
              <span
                v-if="activeSection === link.section"
                class="absolute bottom-1 left-1/2 -translate-x-1/2 w-1 h-1 rounded-full bg-emerald-500"
              ></span>
            </a>
          </li>
        </ul>

        <!-- CTA Button Desktop -->
        <a
          href="#contact"
          class="hidden md:inline-flex items-center gap-2 px-4 py-2 bg-emerald-600 hover:bg-emerald-700 text-white text-sm font-semibold rounded-xl shadow-sm shadow-emerald-600/20 hover:-translate-y-0.5 transition-all duration-200"
        >
          Hire Me
          <svg
            class="w-3.5 h-3.5"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2.5"
              d="M17 8l4 4m0 0l-4 4m4-4H3"
            />
          </svg>
        </a>

        <!-- Hamburger -->
        <button
          @click="isOpen = !isOpen"
          type="button"
          class="flex md:hidden text-slate-600 hover:text-emerald-500 hover:bg-emerald-50 p-2 rounded-lg focus:outline-none transition-colors"
          aria-label="Toggle menu"
        >
          <svg
            class="h-5 w-5"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              v-if="!isOpen"
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
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

    <!-- Mobile Menu -->
    <transition
      enter-active-class="transition-all duration-300 ease-out"
      enter-from-class="opacity-0 -translate-y-2"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition-all duration-200 ease-in"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 -translate-y-2"
    >
      <div
        v-show="isOpen"
        class="md:hidden border-t border-emerald-50 bg-white/98 backdrop-blur-md"
      >
        <ul class="px-4 pt-2 pb-5 space-y-1 font-medium">
          <li v-for="link in navLinks" :key="link.section">
            <a
              :href="link.href"
              @click="closeMenu"
              :class="[
                'flex items-center gap-3 px-4 py-2.5 rounded-xl text-sm transition-all duration-200',
                activeSection === link.section
                  ? 'bg-emerald-50 text-emerald-600 font-semibold'
                  : 'text-slate-600 hover:bg-emerald-50/60 hover:text-emerald-600',
              ]"
            >
              <span
                :class="[
                  'w-1.5 h-1.5 rounded-full transition-colors duration-200',
                  activeSection === link.section
                    ? 'bg-emerald-500'
                    : 'bg-slate-300',
                ]"
              ></span>
              {{ link.label }}
            </a>
          </li>
          <li class="pt-2">
            <a
              href="#contact"
              @click="closeMenu"
              class="flex items-center justify-center gap-2 px-4 py-2.5 bg-emerald-600 hover:bg-emerald-700 text-white text-sm font-semibold rounded-xl transition-colors duration-200"
            >
              Hire Me
              <svg
                class="w-3.5 h-3.5"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2.5"
                  d="M17 8l4 4m0 0l-4 4m4-4H3"
                />
              </svg>
            </a>
          </li>
        </ul>
      </div>
    </transition>
  </nav>
</template>
