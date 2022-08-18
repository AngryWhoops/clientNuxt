<template>
  <div>
    <h1>Фид лента, Корень</h1>
    <PostListComponentVue :posts="posts" />
  </div>

</template>

<script>
import PostListComponentVue from '~/components/PostListComponent.vue';
export default {
  async asyncData({ $axios }) {
    const posts = await $axios.$get('getallmyposts');
    return { posts };
  },
  components: {
    PostListComponentVue
  }
}
</script>

<style scoped>
</style>
