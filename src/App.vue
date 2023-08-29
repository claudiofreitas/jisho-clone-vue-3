<script setup lang="ts">
import { RouterView } from 'vue-router';
import SearchBar from '@/components/SearchBar.vue'
</script>

<template>
  <header>Header</header>
  <SearchBar />

  <RouterView />
</template>

<style scoped></style>
