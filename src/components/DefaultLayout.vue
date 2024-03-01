<script setup>
import NavBar from "../components/NavBar.vue";
</script>
<template>
  <div class="max-w-[1200px] mx-auto">
    <NavBar />
    <main>
      <router-view />
    </main>
  </div>
</template>
