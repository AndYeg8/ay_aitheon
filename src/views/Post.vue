<template>
  <div>
    <!-- <router-link to="/">Posts List</router-link> -->
      <blog-post v-bind:title="post.title"></blog-post>
      <h1>Single post</h1>
          <div>
            <h2>{{this.post.title}}</h2>
            <p>{{this.post.body}}</p>
          </div>
  </div>
</template>

<script>
export default {
  name: 'Post',
	computed: {
		singlePost () {
			return this.post.id
		}
  }
}
</script>