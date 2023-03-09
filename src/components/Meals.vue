<template>

  <div v-if="!meals.length" class="flex justify-center text-red-900 font-bold p-8">
    There are no Foods
  </div>
  <div class="grid grid-cols-1 md:grid-cols-3 gap-5 px-8">
    <MealItem v-for="meal of meals" :key="meal.idMeal" :meal="meal" />
  </div>
</template>

<script setup>
import MealItem from './MealItem.vue';
const { meals } = defineProps({
  meals: {
    required: true,
    type: Array,
  }
})

</script>
