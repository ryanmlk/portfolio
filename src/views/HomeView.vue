<script setup lang="ts">
import { Smoothie } from "vue-smoothie";
import NavBar from '@/components/NavBar.vue';
import IntroSection from "@/components/IntroSection.vue";
import AboutSection from "@/components/AboutSection.vue";
import createScrollSnap from 'scroll-snap';
</script>

<script lang="ts">
export default {
  components: {
    IntroSection: IntroSection,
    AboutSection: AboutSection
  },
  mounted: function () {
    const scrollContainer = document.getElementById('scrollContainer');
    if (scrollContainer) {
      createScrollSnap(scrollContainer, {
        snapDestinationX: '0%',
        snapDestinationY: '100%',
        timeout: 100,
        duration: 100,
        threshold: 0.1,
        snapStop: false,
      })
    }
  }
}
</script>

<template>
  <main>
    <NavBar />
    <Smoothie id="scrollContainer" class="scrollContainer">
        <IntroSection />
        <AboutSection />
    </Smoothie>
  </main>
</template>

<style lang="scss" scoped>
main {
  background-color: var(--primary-color);
  width: 100vw;
  overflow-x: hidden;
}

.scrollContainer {
  overflow-y: scroll;
  overflow-x: hidden;
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
  max-width: 100vw;
  padding: 100px;
}

@media(max-width: 575px) {
  .root {
    padding: 80px 20px 20px 20px;
  }
}
</style>
