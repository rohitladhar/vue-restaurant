<template>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-5 p-8">
        <MealItem 
            v-for="meal of meals" 
            :key="meal.idMeal"
            :meal="meal"
        />
    </div>
</template>
<script setup>

import {onMounted,ref} from 'vue';
import {useRoute} from 'vue-router'
import {computed} from '@vue/reactivity'
import store from '../store'
import MealItem from '../components/MealItem.vue'
const route = useRoute()
const meals = computed(()=>store.state.mealsByIngredient)


onMounted(()=>{
    store.dispatch('searchMealsByIngredient',route.params.ingredient)
})

</script>