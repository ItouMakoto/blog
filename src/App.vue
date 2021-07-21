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
</style>
