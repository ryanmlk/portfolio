<script setup lang="ts">
import { Smoothie } from "vue-smoothie";
import NavBar from '@/components/NavBar.vue';
import IntroSection from "@/components/IntroSection.vue"
import AboutSection from "@/components/AboutSection.vue"
</script>

<template>
  <main>
    <NavBar />
    <Smoothie id="scrollContainer" class="scrollContainer" :weight="0.2">
      <IntroSection />
      <AboutSection />
    </Smoothie>
  </main>
</template>

<style scoped>
main {
  background-color: var(--primary-color);
  width: 100vw;
  height: 100vh;
  height: 100svh;
  overflow-x: hidden;
}

.scrollContainer {
  overflow-y: scroll;
  height: 100vh;
  height: 100svh;
  width: 100%;
  scrollbar-width: none;
  -ms-overflow-style: none;

  &::-webkit-scrollbar {
    display: none;
  }
}

@media(max-width: 1399px) {}

@media(max-width: 1199px) {}

@media(max-width: 991px) {}

@media(max-width: 767px) {}

@media(max-width: 575px) {}
</style>

<style>
section {
  height: 100vh;
  height: 100svh;
  width: 100vw;
  padding: 100px;
}

@media(max-width: 575px) {
  .root {
    padding: 80px 20px 20px 20px;
  }
}
</style>
