<template>
    <div class="container">
        <h1>Blogs</h1>
        <div class="card mb-3" v-for="post in posts" :key="post.id">
        <div class="card-body">
            <h3 class="card-title"> {{ post.title}} </h3>
            <p class="card-text"> {{ post.body}} </p>
        </div>
        </div>        
    </div>
</template>

<script>
import axios from 'axios'

export default {
 data (){
     return {
         posts:[]
     }
 },
  asyncData (context) {
     return axios.get('https://jsonplaceholder.typicode.com/posts').then((res) =>{
          return {posts: res.data}
      })
  }
}
</script>

<style>

</style>
