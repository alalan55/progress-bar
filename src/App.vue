<script setup>
import progressBarVue from "./components/progressBar.vue";
</script>

<template>
  <main style="padding: 2rem 0 ;  max-width: 1000px; margin: 0 auto;">
    <progressBarVue :has-message="true" message="Carregando informações.."/>
  </main>
</template>

<style scoped></style>
