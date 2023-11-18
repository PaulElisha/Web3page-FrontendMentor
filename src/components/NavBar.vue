<script setup>
import { ref } from 'vue'
import Menubar from 'primevue/menubar'
import nav from '../data/Nav.json'

const items = ref(nav)
</script>

<template>
  <div class="card">
    <Menubar class="menubar" :model="items">
      <template #start>
        <img src="../assets/logo.svg" alt="" />
      </template>
      <template #item="{ item, props }">
        <a v-ripple class="flex align-items-center navItem" v-bind="props.action">
          <span class="ml-2">{{ item.label }}</span>
        </a>
      </template>
    </Menubar>
  </div>
</template>

<style scoped>
.card {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Inter', sans-serif;
}
.menubar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 1200px;
  margin: 10px auto;
  padding: 30px;
}

img {
  cursor: pointer;
}
.navItem {
  color: hsl(236, 13%, 42%);
  font-size: 15px;
  transition: 1s linear;
}

.navItem:hover {
  color: hsl(5, 85%, 63%);
}
</style>
