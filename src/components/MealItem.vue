<script setup>
import YouTubeButton from "./YouTubeButton.vue";
const { meal } = defineProps({
  meal: {
    type: Object,
    required: true,
  },
});
</script>
<template>
  <div class="bg-white shadow rounded-xl hover:scale-105 transition-all">
    <router-link :to="{ name: 'mealDeatails', params: { id: meal.idMeal } }">
      <img
        class="rounded-t-xl w-full h-48 object-cover"
        :src="meal.strMealThumb"
        :alt="meal.strMeal"
      />
    </router-link>

    <div class="p-3">
      <h3 class="p-3 font-bold">{{ meal.strMeal }}</h3>
      <p class="mb-4">
        {{ $filters.truncateWords(meal.strInstructions, 20) }}
      </p>
      <div class="flex items-center justify-between">
        <YouTubeButton :href="meal.strYoutube">YouTube</YouTubeButton>
      </div>
    </div>
  </div>
</template>
