<template>
<div class="container">  
    <div class="card">
        <div v-if="peliculas.id === 1">
            <img 
                class="card-img-top" 
                src= "../assets/imagenes/pinocho.jpg"
                alt="Card image cap">
            <div class="card-body"        >
            <h5 class="card-title">"Pinocho"</h5>
            <p class="card-text">"Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque, sapiente."</p>
            </div>
        </div> 
        <div v-else-if="peliculas.id === 2">
            <img 
                class="card-img-top" 
                src= "../assets/imagenes/wakanda.jpg"
                alt="Card image cap">
            <div class="card-body"        >
            <h5 class="card-title">"Wakanda Forever"</h5>
            <p class="card-text">"Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque, sapiente."</p>
            </div>
        </div> 
        <div v-else>
            <img 
                class="card-img-top" 
                src= "../assets/imagenes/simpson.jpg"
                alt="Card image cap">
            <div class="card-body"        >
            <h5 class="card-title">"Simpson"</h5>
            <p class="card-text">"Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque, sapiente."</p>
            </div>
        </div> 
    </div>
</div>
</template>

<script setup>

import { defineProps } from 'vue'

defineProps({
  peliculas: Array,
});



</script>

<style>

</style>