<script setup lang="ts">
import NavBar from '@/components/NavBar.vue';
</script>

<template>
  <main>
    <NavBar/>
    <div class="root">
      <div class="leftSection">
        <h2>HI I'M</h2>
        <h1>RYAN</h1>
        <p>Full-stack software engineer with a passion for learning and creating elegant solutions</p>
      </div>
      <div class="rightSection">
        <img class="hero" src="/images/hero.png">
      </div>
    </div>
  </main>
</template>

<style scoped>
  main {
    background-color: var(--primary-color);
    width: 100vw;
    height: 100vh;
  }

  .root {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: row;
    align-items: center;
    padding: 100px;
    color: var(--secondary-color);

    .leftSection {
      flex: 1;
      h1 {
        font-weight: 600;
        margin-left: -8px;
        line-height: 95px;
        font-family: var(--primary-font);
        font-size: 96px;
      }
      h2 {
        font-weight: 600;
        font-family: var(--primary-font);
        font-size: 27px;
      }
      p{
        font-weight: 600;
        margin-top: 22px;
        font-family: var(--secondary-font);
        font-size: 24px;
        width: 90%;
        line-height: 30px;
      }
    }

    .rightSection {
      flex: 1;
      display: flex;
      align-items: center;

      .hero {
        max-width: 100%;
        max-height: 100%;
      }
    }
  }
</style>
