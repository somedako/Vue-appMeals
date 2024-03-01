<script setup>
const props = defineProps({
  href: {
    type: String,
  },
});
</script>

<template>
  <a
    class="px-3 py-2 rounded border-2 text-white border-red-600 bg-red-500 hover:bg-red-600 hover:text-white transition-colors"
    :href="href"
    target="_blank"
    ><slot
  /></a>
</template>
