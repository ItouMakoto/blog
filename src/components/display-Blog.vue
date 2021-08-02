<template>
<div id="showBlog" v-theme:attributes="'narrow'">
  <h1>博客总揽</h1>
  <div class="single-blog" v-for="item in blogs">
    <h2 v-rainbow>{{item.title}}</h2>
    <article>
      {{item.body}}
    </article>
  </div>
</div>
</template>

<script>
import axios from 'axios'
import blogdata from '@/assets/posts.json'
import Vue from 'vue'
Vue.directive('rainbow',{
  bind:function(el,binding,vnode){
    let color='#'+Math.random().toString(16).slice(2,8)
    el.style.color=color
  }
})
Vue.directive('theme',{
  bind:function(el,binding,vnode){
    console.log('value',binding.value)
    console.log('arg',binding.arg)
    console.log('arg',binding.arg[0])
  }
})
export default {
  name: 'display-Blog',
  data(){
    return{
      blogs:[]
    }

  },
  created(){
    axios.get('http://jsonplaceholder.typicode.com/posts').then(res=>{
      this.blogs=blogdata
    })
  }
}
</script>

<style scoped>
#showBlog{
  max-width: 800px;
  margin: 0 auto;
}
.single-blog{
  padding:20px;
  margin: 20px 0;
  box-sizing: border-box;
  background-color: #eee
}
</style>
