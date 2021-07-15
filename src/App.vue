<template>
  <div id="app">
    <blogmain></blogmain>
    <addblog></addblog>
  </div>
</template>

<script>
import blogmain from './components/blog-main'
import addblog from './components/add-blog'
export default {
  name: 'App',
  components: {
    blogmain,
    addblog
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
  margin-top: 60px;
}
</style>
