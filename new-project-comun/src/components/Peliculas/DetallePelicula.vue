<template>
<div class="container">  
    <div class="card" v-for="pelicula in peliculas" :key="pelicula.id">
        <div v-if=" idePeliculas === pelicula.id"> 
            <img 
                class="card-img-top" 
                :src= "pelicula.src"
                alt="Card image cap">
            <div class="card-body">
            <h5 class="card-title">{{ pelicula.name }}</h5>
            <p class="card-text">{{ pelicula.description }}</p>
            </div>
        </div> 
    </div>
</div>
    <a @click="handleBack" class="btn btn-primary">Go To Home</a>
</template>

<script setup>

import { defineProps, defineEmits } from 'vue'

defineProps({
  peliculas: Array,
  idePeliculas: Number,
});

const emit = defineEmits(['goto'])


function handleBack() {
        emit("goto", 0)      
    }

</script>

<style scoped>

</style>