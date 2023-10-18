<template>
    <div class="flex flex-col p-8">
        
        <pre>
            {{ ingredients }}
        </pre>
    </div>
</template>
<script setup>
import {computed ,onMounted,ref} from 'vue';
import store from '../store';
import axiosClient from '../axiosClient';
import MealsByLetter from './MealsByLetter.vue';
const meals = computed(()=>store.state.meals)


const ingredients = ref([])

onMounted(async()=>{
    const response = await axiosClient.get('/list.php?i=list')
    ingredients.value = response.data
})
</script>