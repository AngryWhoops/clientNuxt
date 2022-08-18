<template>
  <div>
    <PostComponentVue v-for="post in posts" :key="post.id" :post="post" />

  </div>
</template>

<script>
import PostComponentVue from './PostComponent.vue';

export default {
  props: {
    posts: {
      type: Array,
      required: true
    }
  },
  components: {
    PostComponentVue
  },
}
</script>

<style scoped>
</style>
