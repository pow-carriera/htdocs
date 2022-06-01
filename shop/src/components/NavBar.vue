<template>
  <div class="navbar">
    <div class="topnav">
      <a class="active" href="#/">Home</a>
      <a href="#/login">News</a>
      <a href="#/notfound">Contact</a>
      <a href="#about">About</a>
      
    </div>
  </div>
  <component :is="currentView" />
</template>
<script>
import Home from './HelloWorld.vue'
import Login from './Login.vue'
import NotFound from './NotFound.vue'

const routes = {
  '/': Home,
  '/login': Login,
  '/notfound' : NotFound
}

export default {
  data() {
    return {
      currentPath: window.location.hash
    }
  },
  computed: {
    currentView() {
      return routes[this.currentPath.slice(1) || '/'] || NotFound
    }
  },
  mounted() {
    window.addEventListener('hashchange', () => {
    this.currentPath = window.location.hash
		})
  }
}
</script>