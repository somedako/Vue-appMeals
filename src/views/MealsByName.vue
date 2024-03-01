<script setup>
import { ref, computed, onMounted } from "vue";
import store from "../store";
import { useRoute } from "vue-router";
import Meals from "../components/Meals.vue";

const route = useRoute();
const text = ref("");
const meals = computed(() => store.state.searchedMeals);

const seacrMeals = () => {
  if (text.value) {
    store.dispatch("searchMeals", text.value);
  } else {
    store.commit("setSearchedMeals", []);
  }
};

onMounted(() => {
  text.value = route.params.name;
  if (text.value) {
    seacrMeals();
  }
});
</script>
<template>
  <div class="p-8 pb-0">
    <input
      type="text"
      v-model="text"
      class="rounded border-2 border-gray-200 w-full"
      placeholder="Search for meals"
      @change="seacrMeals"
    />
  </div>

  <div class="grid grid-cols-1 md:grid-cols-3 gap-5 p-8">
    <Meals :meals="meals" />
  </div>
</template>
