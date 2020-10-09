<template>
  <div class="container">
    <article>
      <h1 class="title">{{post.title}}</h1>
      <p>{{post.content}}</p>
    </article>
    <aside>
      <h3>post you might enjoy</h3>
      <ul>
        <li v-for="related in relatedPosts" :key="related.id">
          <nuxt-link :to="`/posts/${related.id}`">{{related.title}}</nuxt-link>
        </li>
      </ul>
    </aside>
  </div>
</template>
<script>
export default {
  data() {
    return {
      id: this.$route.params.id
    };
  },
  head() {
    return {
      title: this.post.title
    };
  },
  computed: {
    post() {
      return this.$store.state.posts.all.find(post => post.id === this.id);
    },
    relatedPosts() {
      return this.$store.state.posts.all.filter(post => post.id !== this.id);
    }
  }
};
</script>
<style >
.container {
  display: flex;
  /* align-items: flex-start; */
  justify-content: space-between;
  line-height: 1.5;
}
article * {
  margin-bottom: 1em;
}
aside {
  min-width: 17.5em;
  max-width: 17.5em;
  padding-left: 2em;
}
</style>
