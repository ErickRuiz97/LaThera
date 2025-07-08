<template>
  <div class="d-flex align-items-start">
    <img :src="icon" alt="Icon" width="48" class="me-3 flex-shrink-0" />
    <div>
      <span class="d-block title mb-1"><span class="me-2">{{ index }}.</span>{{ title }}</span>
      <small>{{ text }}</small>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps(
  {
    icon: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    text: {
      type: String,
      required: true
    },
    index: { type: Number, required: true }
  }
)
</script>

<style scoped>
.title {
  color: #5a7263;
}
</style>
