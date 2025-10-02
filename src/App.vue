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
  </div>
</template>

<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { ref } from 'vue'
import HelloWorld from './components/HelloWorld.vue'
const props = defineProps<{ name?: string }>()
const count = ref(0)
const name = 'Meriem'
</script>
<style>
.happy {
  padding: 12px;
  font-size: 70px;
}
</style>
