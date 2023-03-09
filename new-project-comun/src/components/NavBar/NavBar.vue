<template>

  <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarNavAltMarkup">
    <div class="navbar-nav">
      <a class="nav-item nav-link"><router-link to="/">Home</router-link></a>
      <a class="nav-item nav-link"><router-link to="/about">Reviews</router-link></a>     
    </div>
  </div>
</nav>
</template>

<style scoped>
  nav{
    margin-bottom: 5%;
  }
  .navbar-nav{
    text-align: center;
    width: auto;
    padding-left: 45%;
    
  }
  a{
    text-decoration: none;
    color:white;
  }

</style>