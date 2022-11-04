<script setup lang="ts">
import WordList from '../components/WordList.vue'
</script>

<template>
  <main>
    <WordList/>
  </main>
</template>


<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
