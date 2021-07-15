<template>
  <div>
    <h2>添加博客</h2>
    <form action="">
      <label for="blog-title">博客标签</label>
      <input type="text" required v-model="blog.title" id="blog-title">
      <label for="blog-content">博客内容</label>
      <textarea v-model="blog.content" id="blog-content"></textarea>
      <div id="check-class">
        <input type="checkbox" v-model="blog.blogClass" value="Vue.js">
        <label for="">Vue.js</label>
        <input type="checkbox" v-model="blog.blogClass" value="node.js">
        <label for="">node.js</label>
        <input type="checkbox" v-model="blog.blogClass" value="React.js">
        <label for="">React.js</label>
        <input type="checkbox" v-model="blog.blogClass" value="typescript.js">
        <label for="">typescript.js</label>

      </div>
    </form>
    <hr>
    <div id="preview">
      <h3>总览</h3>
      <p>博客标题:{{blog.title}}</p>
      <p>博客内容:</p>
      <p>{{blog.content}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'add-blog',
  data(){
    return{
      blog:{
        title: '',
        content:'',
        blogClass:[]
      }
    }
  }
}
</script>

<style scoped>

</style>
