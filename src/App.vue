<template>
  <div id="app">
    <router-link to="/" exact>List of Posts:</router-link>
    
      <div class="posts" v-for="post in posts" :key="post.id">
        <h2>{{post.title}}</h2>
        <p>{{post.body}}</p>
        <!-- <button v-on:click="showPost">More detail</button> -->
        <router-link tag="button" :to="'/Post/'+ post.id">
          More detail
        </router-link>
        <router-view/>
      </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      posts: []
    }
  },
  async mounted (){
    const res = await fetch('https://jsonplaceholder.typicode.com/posts?_limit=10');
    const posts = await res.json();
    this.posts = posts;
  }
};
</script>

<style>
#app {
  margin: 60px auto;
  width: 400px;
}
.posts {
  border: 1px solid;
  border-radius: 5px;
  margin-bottom: 1rem;
}
</style>
