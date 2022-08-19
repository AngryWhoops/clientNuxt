<template>
  <div>
    <form @submit.prevent>
      <InputFieldComponentVue @input-string="userLogin = $event" placeholder="Логин пользователя" />
      <ButtonComponentVue @click="findPosts()">Найти</ButtonComponentVue>
    </form>
    <PostListComponentVue :posts="posts" />
  </div>
</template>

<script>
import InputFieldComponentVue from '~/components/InputFieldComponent.vue';
import ButtonComponentVue from '~/components/ButtonComponent.vue';
import PostListComponentVue from '~/components/PostListComponent.vue';

export default {
  data() {
    return {
      userLogin: '',
      posts: []
    }
  },
  components: {
    InputFieldComponentVue,
    ButtonComponentVue,
    PostListComponentVue
  },
  methods: {
    async findPosts() {
      this.posts = await this.$axios.$get('getpostsbyuser/' + this.userLogin);
    }
  }
}
</script>

<style scoped>
</style>
