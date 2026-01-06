<script setup>
import { computed } from 'vue'

const isFirstSlide = computed(() => $nav.currentPage === 1)
</script>

<template>
  <div class="nyx-global-logo">
    <img src="/images/nyx_logo.svg" alt="Nyx" />
  </div>
  <div v-if="!isFirstSlide" class="page-number">
    {{ $nav.currentPage }}
  </div>
</template>

<style scoped>
.nyx-global-logo {
  position: fixed;
  bottom: 20px;
  right: 20px;
  z-index: 100;
  pointer-events: none;
}

.nyx-global-logo img {
  width: 100px;
  height: auto;
}

.page-number {
  position: fixed;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  font-family: 'BIZ UDPMincho', serif;
  font-size: 14px;
  color: #000000;
  z-index: 100;
}
</style>
