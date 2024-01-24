<script setup lang="ts">
import gsap from 'gsap';
import { Rive } from "@rive-app/canvas";
import createScrollSnap from 'scroll-snap';
import { Smoothie } from "vue-smoothie";
import NavBar from '@/components/NavBar.vue';
import IntroSection from "@/components/IntroSection.vue"
import AboutSection from "@/components/AboutSection.vue"
</script>

<script lang="ts">
export default {
  mounted: function () {
    new Rive({
      src: "/images/dev.riv",
      canvas: document.getElementById("hero") as HTMLCanvasElement,
      autoplay: true,
    })

    gsap.to(".hero", {
      alpha: 1,
      delay: 1,
      duration: 1,
    });

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
  },
  methods: {
    // where the animation will start from
    beforeEnter(el: any) {
      el.style.opacity = '0'
      el.style.transform = 'translateY(-100px)'
    },
    // where the animation will end up
    enter(el: any) {
      gsap.to(el, {
        duration: 1,
        y: 0,
        opacity: 1,
      })
    }
  }
}
</script>

<template>
  <main>
    <NavBar />
       <Smoothie id="scrollContainer" class="scrollContainer" :weight="0.2">
        <IntroSection/>
        <AboutSection/>
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

    &:nth-last-of-type(1) {
      height: calc(100vh - 70px);
      height: calc(100svh - 70px);
    }
  }
</style>
