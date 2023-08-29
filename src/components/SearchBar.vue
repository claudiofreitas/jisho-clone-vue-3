<script setup lang="ts">
import { ref } from 'vue'

const searchInput = ref<string | null>(null)
</script>

<template>
<div class="overlay">
  <div class="inner">
    <div class="type-selector">All</div>
    <input type="text" name="keyword" tabindex="1" placeholder="English, Japanese, Romaji, words or text" v-model="searchInput"/>
    <button>S</button>
  </div>
</div>
</template>

<style scoped>
* {
  font-family: "Helvetica Neue";
}

.type-selector {
  color: #eee;
  font-size: 14px;
  padding: 4px 12px;
}

input {
  font-size: 22px;
  width: 100%;
  color: #eee;
  background: none;
  border: none;
  height: 34px;
  box-shadow: none;

  appearance: none;
  -webkit-appearance: none;
  -moz-appearance: none;
  outline: none;
}

.overlay {
  background: #6e6e6e;
  padding: 4px;
  border-radius: 5px;
}

.inner {
  display: flex;
  align-items: center;
  background: #404040;
  padding: 4px;
}
</style>
