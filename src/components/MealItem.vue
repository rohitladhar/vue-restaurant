<template>
    <div class="bg-white shadow rounded-xl" >
            <router-link :to="{name:'mealDetails',params:{id:meal.idMeal}}">
                <img :src="meal.strMealThumb" alt ="meal.strMeal" class="rounded-t-xl h-48 w-full object-cover"/>
            </router-link>
            <div>
                <h3 class="font-bold m-2">{{ meal.strMeal }}</h3>
                <p class="m-2">
                    Dummy Text Dummy Text Dummy Text Dummy Text Dummy Text Dummy Text Dummy Text Dummy Text Dummy Text
                </p>
                <div class="m-2 flex items-center justify-between">
                    <YoutubeButton :href="meal.strYoutube">Youtube</YoutubeButton>
                </div>
            </div>
        </div>
</template>

<script setup>
import YoutubeButton from '../components/youtubebutton.vue'
const {meal} = defineProps({
    meal:{
        required:true,
        type:Object
    }
})
</script>