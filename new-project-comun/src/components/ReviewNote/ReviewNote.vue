<template>

  <div class="cards-container">
                <div v-for="(review,index) in reviews" :key="index" class="card">    
                    <p class="usuario">{{review.name}}:</p>
                    <h3>{{ review.title }}</h3>
                    <h5>{{ review.text }}</h5>
                    <p class="date">{{ review.date.toLocaleDateString("en-eu") }}</p>
                </div>
            </div>

</template>

<script>
export default{
  props: {
    reviews: Array,
  }
}

</script>

<style scoped>
 .cards-container{
  display: flex;
  border:1px solid;
  flex-wrap: wrap;
  border: none  ;
  border-top: 1px solid;
 
 }
 .card{
  width: 47%;
  padding: 1rem;
  margin: 1rem;
  background-color: antiquewhite;
 }

 .usuario{
  text-align: left;
 }
</style>