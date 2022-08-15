<template>
  <div>
    <h1>Посты по хештегам</h1>
    <InputFieldComponent :customFunction="find()" />
    <PostListComponentVue :apiEndPoint="methodString" />
  </div>
</template>

<script>
import PostListComponentVue from '~/components/PostListComponent.vue';
import InputFieldComponentVue from '~/components/InputFieldComponent.vue';

export default {
  data() {
    return {
      methodString: 'getpostsbyhashtag'
    }
  },
  components: {
    PostListComponentVue,
    InputFieldComponentVue,
  },
  methods: {
    find() {
      this.$axios.get(this.methodString).then(response => this.methodString = response.data);
    }
  }
}
</script>

<style scoped>
</style>
