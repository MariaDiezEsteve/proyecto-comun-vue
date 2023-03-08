<template>
    <div id="app">
      <Navbar />
      <router-view/>
      <Footer />
    </div>
</template>

<script>
import Navbar from "../src/components/NavBar/NavBar.vue"
import Footer from "../src/components/NavBar/FooterNav.vue"

export default{
  name: 'app',
  components: {
    Navbar,
    Footer
  }
}

</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
