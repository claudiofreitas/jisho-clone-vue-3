<script setup lang="ts">
import { ref } from 'vue'
import MagnifyGlass from './MagnifyGlass.vue'

const emit = defineEmits<{
  onSearch: [keyword: string]
}>()

const searchInput = ref<string | null>(null)
const isOpened = ref(false)

function submitSearch() {
  if (searchInput.value) {
    emit('onSearch', searchInput.value)
  }
}
</script>

<template>
<div class="wrapper">
  <div class="overlay" :class="{'opened-styles': isOpened}">
    <div class="inner">
      <div class="type-selector" @click="isOpened = !isOpened"><span>All</span><span>▾</span></div>
      <input type="text" name="keyword" tabindex="1" placeholder="English, Japanese, Romaji, words or text" v-model="searchInput"/>
      <button class="search-button" @click="submitSearch">
        <MagnifyGlass />
      </button>
    </div>
  </div>
</div>
</template>

<style scoped>
* {
  font-family: "Helvetica Neue";
}

.wrapper {
  padding: 4px;
}

.type-selector {
  color: #eee;
  font-size: 14px;
  padding: 4px 12px;
  color: #aaa;
  display: flex;
  gap: 3px;
  border-right: solid 1px #888;
  margin-right: 6px;
  cursor: pointer;
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
  transition: all 150ms ease-in-out;
}

.inner {
  display: flex;
  align-items: center;
  background: #404040;
  padding: 4px;
  border-radius: 2px;
}

.opened-styles {
  height: 400px;
  padding: 8px;
}

.search-button {
  background-color: #6a6a6a;
  color: #ddd;
  height: 36px;
}
</style>
