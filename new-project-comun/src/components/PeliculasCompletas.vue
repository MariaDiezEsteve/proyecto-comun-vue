<template>
<div class="container">  
      <div class="card" v-for="pelicula in peliculas" :key="pelicula">
        <img 
            class="card-img-top" 
            :src= "pelicula.src"
            alt="Card image cap"
            @click="mostrarDescription = true"
            @dblclick="mostrarDescription = false"
        >
        <div 
          class="card-body"
          v-show="mostrarDescription"
        >
          <h5 class="card-title">{{ pelicula.name }}</h5>
          <p class="card-text">{{ pelicula.description }}</p>
          <a  @click="handleNext" class="btn btn-primary">Go To Details</a> 
        </div>
      </div>
</div>


</template>

<script setup>
import { ref, defineEmits, defineProps } from 'vue'

defineProps({
  peliculas: Array,
});

const mostrarDescription = ref(false)

const emit = defineEmits(['goto'])

function handleNext() {
        emit("goto", 1)      
    }

</script>


<style scoped>
.container{
  display: flex;
}
.card{
  width: 18rem;
}
</style>