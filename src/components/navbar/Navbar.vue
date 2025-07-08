<script setup>
import { ref } from 'vue'
import logo from '@/assets/images/LaThera Logo.png'

const emit = defineEmits(['menuSelected'])
const activeIndex = ref('blog')

const options = [
  { key: 'home', label: 'Home for professionals' },
  { key: 'therapist', label: 'Find a Therapist' },
  { key: 'about', label: 'About' },
  { key: 'blog', label: 'Blog' },
  { key: 'contact', label: 'Contact' },
]
const mobileVisibleCount = 1
const moreOpen = ref(false)
const handleSelect = (key) => {
  activeIndex.value = key
  emit('menuSelected', key)
  moreOpen.value = false
}
</script>
<template>
  <header class="navbar">
    <div class="navbar-left">
      <img :src="logo" alt="Logo" class="logo" />
    </div>

    <nav class="navbar-menu desktop-menu">
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

    <nav class="navbar-menu mobile-menu">
      <a
        v-for="opt in options.slice(0, mobileVisibleCount)"
        :key="opt.key"
        href="#"
        class="navbar-item"
        :class="{ active: activeIndex === opt.key }"
        @click.prevent="handleSelect(opt.key)"
      >
        {{ opt.label }}
      </a>
      <div class="more-container">
        <button class="navbar-item more-button" @click="moreOpen = !moreOpen" aria-label="Más opciones">
          ☰
        </button>
        <div v-if="moreOpen" class="more-dropdown">
          <a
            v-for="opt in options.slice(mobileVisibleCount)"
            :key="opt.key"
            href="#"
            class="navbar-item"
            :class="{ active: activeIndex === opt.key }"
            @click.prevent="handleSelect(opt.key)"
          >
            {{ opt.label }}
          </a>
        </div>
      </div>
    </nav>
  </header>
</template>

<style scoped>
.navbar {
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #f4f3ee;
  border-bottom: 1px solid #dcdcdc;
  padding: 0.5rem 1.5rem;
  gap: 1.5rem;
  flex-wrap: nowrap;
  max-width: 100vw;
  box-sizing: border-box;
}

.navbar-left {
  flex-shrink: 0;
}

.logo {
  height: 60px;
  margin-right: 1rem;
}

.navbar-menu {
  display: flex;
  align-items: center;
  gap: 2rem;
  flex-wrap: nowrap;
  flex-grow: 0;
}

.navbar-item {
  font-size: 0.95rem;
  color: #8c9b8b;
  font-weight: 400;
  text-decoration: none;
  padding: 0.25rem 0.75rem;
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

.more-container {
  position: relative;
  flex-shrink: 0;
}

.more-button {
  background: none;
  border: 1px solid #8c9b8b;
  border-radius: 0.75rem;
  color: #8c9b8b;
  padding: 0.25rem 0.75rem;
  cursor: pointer;
  white-space: nowrap;
  font-size: 1.25rem;
  line-height: 1;
}

.more-dropdown {
  position: absolute;
  top: 100%;
  right: 0;
  background: #f4f3ee;
  border: 1px solid #dcdcdc;
  border-radius: 8px;
  padding: 0.5rem 0;
  margin-top: 0.25rem;
  min-width: 140px;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  z-index: 999;
  display: flex;
  flex-direction: column;
  gap: 0.25rem;
}
.mobile-menu {
  display: none;
}
@media (max-width: 768px) {
  .desktop-menu {
    display: none;
  }
  .mobile-menu {
    display: flex;
    gap: 1rem;
    align-items: center;
    flex-grow: 1;
  }
}

</style>
