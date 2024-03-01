<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import Sidebar from 'primevue/sidebar'
import Button from 'primevue/button'
import { ref } from 'vue'

const visible = ref(false)
</script>

<template>
  <header class="mb-4 bg-orange-900 py-4 text-white sm:mb-8 sm:py-6">
    <nav class="hidden sm:flex sm:justify-center">
      <RouterLink class="mr-8" to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
    <div class="flex justify-end">
      <Sidebar v-model:visible="visible" header="Cookbook">
        <nav @click="visible = false" class="flex flex-col">
          <RouterLink class="mb-2" to="/">Home</RouterLink>
          <RouterLink to="/about">About</RouterLink>
        </nav>
      </Sidebar>
      <Button class="mr-6 sm:hidden" @click="visible = true">
        <i class="pi pi-bars text-4xl" />
      </Button>
    </div>
  </header>
  <RouterView />
</template>
