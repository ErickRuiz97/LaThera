<script setup>
import { ref, onMounted, onUnmounted, computed, watch } from 'vue';
import logo from '@/assets/images/LaThera Logo.png';

const emit = defineEmits(['menuSelected']);
const activeIndex = ref('blog');
const isMobileMenuOpen = ref(false);
const screenWidth = ref(window.innerWidth);

const options = [
  { key: 'home', label: 'Home for professionals' },
  { key: 'therapist', label: 'Find a Therapist' },
  { key: 'about', label: 'About' },
  { key: 'blog', label: 'Blog' },
  { key: 'contact', label: 'Contact' },
];

const debounce = (func, delay) => {
  let timeout;
  return function(...args) {
    const context = this;
    clearTimeout(timeout);
    timeout = setTimeout(() => func.apply(context, args), delay);
  };
};

const handleResize = debounce(() => {
  screenWidth.value = window.innerWidth;
  if (screenWidth.value > 768) {
    isMobileMenuOpen.value = false;
  }
}, 100);

onMounted(() => {
  window.addEventListener('resize', handleResize);
});

onUnmounted(() => {
  window.removeEventListener('resize', handleResize);
});

const handleSelect = (key) => {
  activeIndex.value = key;
  emit('menuSelected', key);
  isMobileMenuOpen.value = false;
};

const isMobileView = computed(() => screenWidth.value <= 768);

watch(isMobileMenuOpen, (newValue) => {
  if (newValue && isMobileView.value) {
    document.body.style.overflow = 'hidden';
  } else {
    document.body.style.overflow = '';
  }
}, { immediate: true });
</script>

<template>
  <header class="navbar">
    <div class="navbar-left">
      <img :src="logo" alt="Logo" class="logo" />
    </div>

    <nav v-if="!isMobileView" class="navbar-menu desktop-menu">
      <a
        v-for="opt in options"
        :key="opt.key"
        href="#"
        class="navbar-item"
        :class="{ active: activeIndex === opt.key }"
        @click.prevent="handleSelect(opt.key)"
      >
        {{ opt.label }}
      </a>
    </nav>

    <div v-if="isMobileView" class="mobile-controls">
      <button
        class="hamburger-button"
        @click="isMobileMenuOpen = !isMobileMenuOpen"
        aria-label="Abrir menú"
        :aria-expanded="isMobileMenuOpen.toString()"
        aria-controls="mobile-menu-dropdown"
      >
        ☰
      </button>
    </div>

    <Transition name="slide-fade">
      <nav
        v-if="isMobileView && isMobileMenuOpen"
        class="navbar-menu mobile-dropdown"
        id="mobile-menu-dropdown"
      >
        <a
          v-for="opt in options"
          :key="opt.key"
          href="#"
          class="navbar-item"
          :class="{ active: activeIndex === opt.key }"
          @click.prevent="handleSelect(opt.key)"
        >
          {{ opt.label }}
        </a>
      </nav>
    </Transition>
  </header>
</template>

<style scoped>
.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #f4f3ee;
  border-bottom: 1px solid #dcdcdc;
  padding: 0.75rem 1rem;
  box-sizing: border-box;
  width: 100%;
}

.navbar-left {
  flex-shrink: 0;
  display: flex;
  align-items: center;
}

.logo {
  height: 50px;
  max-width: 150px;
}

.navbar-menu {
  display: flex;
  align-items: center;
  gap: 1rem;
  flex-wrap: wrap;
}

.navbar-item {
  font-size: 0.85rem;
  color: #8c9b8b;
  font-weight: 400;
  text-decoration: none;
  padding: 0.4rem 0.8rem;
  border-radius: 0.75rem;
  transition: background-color 0.3s, color 0.3s, border 0.3s;
  white-space: nowrap;
  cursor: pointer;
  flex-shrink: 0;
}

.navbar-item:hover {
  background-color: rgba(122, 139, 110, 0.1);
}

.navbar-item.active {
  border: 1px solid #8c9b8b;
  color: #8c9b8b;
}

.mobile-controls {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.hamburger-button {
  background: none;
  border: 1px solid #8c9b8b;
  border-radius: 0.75rem;
  color: #8c9b8b;
  padding: 0.25rem 0.75rem;
  cursor: pointer;
  font-size: 1.5rem;
  line-height: 1;
  display: flex;
  align-items: center;
  justify-content: center;
  min-width: 44px;
  min-height: 44px;
}

.mobile-dropdown {
  position: absolute;
  top: 60px;
  left: 0;
  width: 100%;
  background: #f4f3ee;
  border-top: 1px solid #dcdcdc;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  z-index: 998;
  flex-direction: column;
  align-items: flex-start;
  padding: 1rem;
  gap: 0.5rem;
}

.mobile-dropdown .navbar-item {
  width: 100%;
  text-align: left;
  padding: 0.75rem 1rem;
  font-size: 1rem;
}

.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: all 0.3s ease-in-out;
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateY(-20px);
  opacity: 0;
}

@media (min-width: 769px) {
  .navbar {
    justify-content: center;
    padding: 0.5rem 1.5rem;
    gap: 1.5rem;
  }

  .logo {
    height: 60px;
    margin-right: 1rem;
  }

  .navbar-menu {
    gap: 2rem;
    flex-grow: 0;
  }

  .navbar-item {
    font-size: 0.95rem;
    padding: 0.25rem 0.75rem;
  }
  .mobile-controls,
  .mobile-dropdown {
    display: none;
  }
}
</style>
