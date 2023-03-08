<template>
  <div class="container">
     <component 
     :is="screens[position]" 
     @goto="handleGoTo"
     :peliculas="peliculas"
     @idpelicula="handleGetData"
     :idePeliculas="idePeliculas"
     />
  </div>
  
</template>

<script>
import PeliculasCompletas from "../components/Peliculas/PeliculasCompletas.vue"
import DetallePelicula from "../components/Peliculas/DetallePelicula.vue"

import { ref }  from "vue"

export default {
    components: {
    PeliculasCompletas,
    DetallePelicula,
  },
    setup(){
    const screens = ["PeliculasCompletas", "DetallePelicula"]
    const position = ref(0)
    const idePeliculas = ref(0)
  

     let handleGoTo = (positions) => { /* Cogerá la posicion del array por eso se pasa como argumento */
     position.value = positions;
   
   }

   let handleGetData = (idPeliculas) => {
      idePeliculas.value = idPeliculas
   }


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
  {
    id:4,
    name: "Spiderman",
    src: require("../assets/imagenes/spiderman.jpg"),
    description: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Itaque, sapiente."
  }
]

    return {
      screens,
      position,
      handleGoTo,
      peliculas,
      handleGetData,
      idePeliculas
    }
  }
}



</script>

<style>

</style>