<template>
  <div class="app-layout">
    <div class="page-card">
      <h1 class="page-title">Hello {{ name }} 👋</h1>

      <p class="intro">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut
        labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco
        laboris nisi ut aliquip ex ea commodo consequat.
      </p>

      <button @click="count++" class="happy-btn">
        If you are happy and you know it click this button {{ count }} times
      </button>

      <UserTable />
    </div>
  </div>
</template>

<script setup lang="ts">
import UserTable from './components/UserTable.vue'
import { ref } from 'vue'

const count = ref(0)
const name = 'Meriem'
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.app-layout {
  min-height: 100vh;
  padding: 2rem;
  background: #f8f9fa;
}

.page-card {
  width: 100%;
  background: #ffffff;
  border-radius: 12px;
  padding: 2rem 2.5rem;
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.08);
}

.page-title {
  margin-bottom: 1rem;
}

.intro {
  margin-bottom: 1.5rem;
  line-height: 1.6;
  color: #444;
}

.happy-btn {
  display: inline-block;
  margin-bottom: 2rem;
  padding: 0.6rem 1.2rem;
  border-radius: 6px;
  border: none;
  background: #ffb347;
  color: #222;
  font-weight: 600;
  cursor: pointer;
  transition:
    transform 0.1s ease,
    box-shadow 0.1s ease;
}

.happy-btn:hover {
  transform: translateY(-1px);
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.15);
}
</style>
