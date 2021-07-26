<template>
  <div id="app">
    <blogmain></blogmain>
    <addblog v-show="false"></addblog>
    <disBlog></disBlog>
  </div>
</template>

<script>
import blogmain from './components/blog-main'
import addblog from './components/add-blog'
import disBlog from './components/display-Blog'
export default {
  name: 'App',
  components: {
    blogmain,
    addblog,
    disBlog
  }
}
</script>

<style>
</style>
