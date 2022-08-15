<template>
  <div>
    <PostComponentVue v-for="post in posts" :key="post.id" :post="post" />

  </div>
</template>

<script>
import PostComponentVue from './PostComponent.vue';

export default {
  created() {
    this.getPosts();
  },
  props: {
    apiEndPoint: {
      type: String,
      requered: true
    }

  },
  data() {
    return {
      posts: []
    }
  },
  components: {
    PostComponentVue
  },
  methods: {
    getPosts() {
      this.$axios.get(this.apiEndPoint).then(response => this.posts = response.data);
    }
  }
}
</script>

<style scoped>
</style>
