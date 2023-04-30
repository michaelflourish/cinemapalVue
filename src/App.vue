<template>
  <NavBar />
  <MyHeader title="Movie Playlist"/>
  <MoviesProp />
  <MyBody project="CinemalPal Project" creator="Olanrewaju Afolayan" crn="CSCI 6655-01" sid="Student ID: 00787323"/>
  <MyFooter />
</template>

<script>
import MyHeader from './components/MyHeader.vue'
import MoviesProp from './components/MoviesProp.vue'
import MyFooter from './components/MyFooter.vue'
import MyBody from './components/MyBody.vue'
import NavBar from './components/NavBar.vue'


export default {
  name: 'App',
  components: {
    NavBar,
    MyHeader,
    MoviesProp,
    MyBody,
    MyFooter
  }
}
</script>

<style>
body{
  background-color: #000;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: #000000;
}
</style>
