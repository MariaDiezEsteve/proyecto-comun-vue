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
          <!-- <a @click ="" class="btn btn-primary">Go somewhere</a> -->
        </div>
      </div>
</div>


</template>

<script setup>
import { ref } from 'vue'

const peliculas = [
  {
    id:1,
    name: "Pinocho",
    src: require("../assets/imagenes/pinocho.jpg"),
    description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque, sapiente."
  },
  {
    id:2,
    name: "Wakanda Forever",
    src: require("../assets/imagenes/wakanda.jpg"),
    description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque, sapiente."
  },
  {
    id:3,
    name: "Simpson",
    src: require("../assets/imagenes/simpson.jpg"),
    description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque, sapiente."
  },
]

const mostrarDescription = ref(false)



</script>


<style scoped>
.container{
  display: flex;
}
.card{
  width: 18rem;
}
</style>