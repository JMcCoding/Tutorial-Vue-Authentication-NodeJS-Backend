<template>
  <div id="app">
    <img src="./assets/logo.png">
    <div>
      <router-link :to="{ name: 'Dashboard' }">Dashboard</router-link>
      <router-link :to="{ name: 'Login' }">Login</router-link>
      <a href="#" @click="logout">Logout</a>
    <router-view/>
  </div>
</template>

<script>
import axios from 'axios'
import router from '@/router'

export default {
  name: 'App',
  methods: {
    logout: e => {
      axios.get('/api/logout')
        .then(() => {
          router.push('/')
        })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
