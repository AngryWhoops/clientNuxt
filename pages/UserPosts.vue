<template>
  <div>
    <h1>Посты юзеров</h1>
    <post-list-component-vue :posts="posts" />
  </div>
</template>

<script>
import PostListComponentVue from '~/components/PostListComponent.vue';

export default {
  async asyncData({ userLogin, $axios }) {
    const posts = await $axios.$get('getpostsbyuser/' + userLogin);
    return { posts };
  },
  components: {
    PostListComponentVue
  }
}
</script>

<style scoped>
</style>
