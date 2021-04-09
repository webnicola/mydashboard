<template>
  <div id="app" class="container">
    <the-header logo="Logo Main" />
    <the-nav />
    <router-view/>
    <the-footer/>
  </div>
</template>
<script>
// @ is an alias to /src
import TheHeader from '@/components/TheHeader.vue'
import TheNav from '@/components/TheNav.vue'
import TheFooter from '@/components/TheFooter.vue'

export default {
  name: 'App',
  components: {
    TheHeader,
    TheNav,
    TheFooter,
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

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

ul {
  list-style-type: none;
  padding: 0;
}
</style>
