<template>
  <div v-if="!clicked.value">
    <img src="./assets/security.svg" class="logo" alt="Security logo" />
    <Title />
  </div>
  <SaveForm :clicked="clicked" />
  <Footer />
</template>

<script setup lang="ts">
import { ref } from "vue";
import Title from "./components/Title.vue";
import SaveForm from "./components/SaveForm.vue";
import Footer from "./components/Footer.vue";

const clicked = ref({ value: false });
</script>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
</style>
