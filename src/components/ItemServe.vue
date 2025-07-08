<template>
  <div
    class="col-md-12 container-serve"
    :style="{ backgroundImage: background, backgroundSize: 'cover', backgroundPosition: 'center' }">
    <div class="p-4 shadow-sm h-100 w-50 float-start" style="transform: scaleX(-1);">
      <img :src="icon" alt="Icon" width="48" class="mb-2" />
      <h2 :style="{ color: titleColor }">{{ title }}</h2>
      <div class="small">
        <template v-if="isList">
          <div class="d-none d-md-block">
            <p v-for="(line, i) in listItemsLines" :key="'desktop-' + i" style="margin: 0;">
              <span
                v-for="(term, j) in line"
                :key="'term-' + j"
                style="margin-right: 10px;"
              >
                <span style="color: black;">•</span> {{ term }}
              </span>
            </p>
          </div>
          <div class="d-block d-md-none">
            <ul class="list-unstyled mb-0">
              <li
                v-for="(line, i) in listItemsLines"
                :key="'mobile-line-' + i"
              >
                <div
                  v-for="(term, j) in line"
                  :key="'mobile-term-' + j"
                  class="d-block mb-1"
                >
                  <span style="color: black;">•</span> {{ term }}
                </div>
              </li>
            </ul>
          </div>
        </template>
        <template v-else>
          <p class="small" style="white-space: pre-line;">{{ text }}</p>
        </template>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  icon: { type: String, required: true },
  title: { type: String, required: true },
  text: { type: String, required: true },
  background: { type: String, default: '#ffffff' },
  titleColor: { type: String, default: '' },
  isList: { type: Boolean, default: false },
  listItemsLines: { type: Array, default: () => [] }
});
</script>

<style scoped>
p {
  font-size: 1.0rem;
  white-space: pre-line;
}

.container-serve {
  position: relative;
  background-size: cover;
  background-position: center;
  border-radius: 16px;
  min-height: 45vh;
  padding: 1rem;
  transform: scaleX(-1);
}
</style>
