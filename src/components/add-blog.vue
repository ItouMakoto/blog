<template>
  <div id="add-blog">
    <h2>添加博客</h2>
    <form action="" v-if="showEditor">
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
      <label for="">作者：</label>
      <select name="" id="" v-model="blog.author">
        <option :value="item" v-for="item in authors">{{item}}</option>
      </select>
      <button @click.prevent="postBlog">提交</button>
    </form>
    <div v-show="!showEditor">
      <h3>提交成功</h3>
    </div>
    <hr v-show="showEditor">
    <div id="preview">
      <h3>总览</h3>
      <p>博客标题:{{blog.title}}</p>
      <p>博客内容:</p>
      <p>{{blog.content}}</p>
      <p>作者：{{blog.author}}</p>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'add-blog',
  data(){
    return{
      showEditor:true,
      authors:['itoumakto','simakaze','ushio'],
      blog:{
        title: '',
        content:'',
        blogClass:[],
        author:''
      }
    }
  },
  mounted () {
    this.blog.author=this.authors[0]
  },
  methods:{
    postBlog(){
      let blog=this.blog
      if(Object.keys(blog).filter(k=>!blog[k]).length>0){
        return
      }
      axios.post('http://jsonplaceholder.typicode.com/posts',{
        title:this.blog.title,
        body:this.blog.content,
        userId:1
      }).then((res)=>{
        if(res.status==201){
          this.showEditor=false
        }
      })
    }
  }

}
</script>

<style scoped>
#add-blog *{
  box-sizing: border-box;
}
#add-blog{
  margin: 20px auto;
  max-width:600px;
  pading: 20px;
}
label {
  display:block;
  margin:20px 0 10px;
}
input[type="text"],textarea,select{
  display:block;
  width:100%;
  padding:8px;
}
textarea{
  height:200px
}
#check-class label {
  display:inline-block;
  margin:0 10px 0 0
}
#check-class input{
  margin-right: 5px;
 }
button{
  display:block;
  margin: 20px 0;
  background:crimson;
  border:0;
  color:white;
  padding:10px;
  border-radius:4px;
  font-size:0.5em;
  cursor:pointer;
 }
#preview{
  margin:0 20px;
  padding:0 10px;
  border:1px dotted #ccc

}
#preview h3{
  margin-top: 10px;
}
</style>
