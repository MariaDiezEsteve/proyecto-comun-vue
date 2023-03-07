<template>
  <div class="container">
     <component 
     :is="screens[position]" 
     
     />
  </div>
  
</template>

<script>
import PeliculasCompletas from "../components/PeliculasCompletas.vue"
import DetallePelicula from "../components/DetallePelicula.vue"

import { ref}  from "vue"

export default {
    components: {
    PeliculasCompletas,
    DetallePelicula,
  },
    setup(){
    const screens = ["PeliculasCompletas", "DetallePelicula"]
    const position = ref(0)


  //   let handleGoTo = (positions) => { /* Cogerá la posicion del array por eso se pasa como argumento */
  //   position.value = positions;
  // }

    return {
      screens,
      position,
      // handleGoTo
    }
  }
}



</script>

<style>

</style>