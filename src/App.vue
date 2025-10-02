<template>
  <div style="padding: 12px; border: 1px solid #ddd; border-radius: 8px">
    <h1>Hello {{ name }} 👋</h1>
    <br />

    <button @click="count++" class="happy">
      It tou are happy and you know it click this button {{ count }} times
    </button>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut
      labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco
      laboris nisi ut aliquip ex ea commodo consequat.
    </p>
    <UserTable />
  </div>
</template>

<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import UserTable from './components/UserTable.vue'
import { ref } from 'vue'
import HelloWorld from './components/HelloWorld.vue'
const props = defineProps<{ name?: string }>()
const count = ref(0)
const name = 'Meriem'
</script>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background: #f8f9fa;
  min-height: 100vh;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
