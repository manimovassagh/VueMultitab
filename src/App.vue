<template>
  <div id="app">
  

<MultiTab/>

        <div id="nav">
      <router-link to="/home">Home</router-link> |
      <router-link to="/contact">Contact</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
    <v-btn @click="pusher">Click me to go to address</v-btn>
   
  </div>
</template>



<script>
// @ is an alias to /src

import MultiTab from "./views/MultiTab.vue"
export default {
  name: 'App',
  components: {
    MultiTab
    
},

  methods: {
    pusher() {
      this.$router.push('/user')
    },
  },


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
</style>
