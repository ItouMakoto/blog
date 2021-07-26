<template>
<div id="showBlog">
  <h1>博客总揽</h1>
  <div class="single-blog" ></div>
</div>
</template>

<script>
import axios from 'axios'
import blogdata from '@/assets/posts.json'
export default {
  name: 'display-Blog',
  data(){
    return{}

  },
  created(){
    axios.get('http://jsonplaceholder.typicode.com/posts').then(res=>{
      console.log(blogdata)
    })
  }
}
</script>

<style scoped>

</style>
