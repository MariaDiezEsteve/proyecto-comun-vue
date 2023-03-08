<template>
  <h2>Reviews</h2>

  <div class="cards-container">
                <div v-for="(review,index) in reviews" :key="index" class="card">
                    <p>{{ review.name}}</p>  
                    <p>{{ review.title }}</p>  
                    <p>{{ review.text }}</p>
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

<style>

</style>