<template>
  <div>
    <h1>Фид лента, Корень</h1>
    <PostListComponentVue :apiEndPoint="methodString" />
  </div>

</template>

<script>
import PostListComponentVue from '~/components/PostListComponent.vue';
export default {
  data() {
    return {
      methodString: 'getallmyposts'
    }
  },
  methods: {

  },
  components: {
    PostListComponentVue
  }
}
</script>

<style scoped>
</style>
