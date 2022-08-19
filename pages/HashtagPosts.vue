<template>
  <div>
    <h1>Посты по хештегам</h1>

    <form @submit.prevent>
      <InputFieldComponentVue @input-string="hashtag = $event" placeholder="Название хештега" />
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
      hashtag: '',
      posts: []
    }
  },
  methods: {
    async findPosts() {
      this.posts = await this.$axios.$get('getpostsbyhashtag/' + this.hashtag);
    }
  },
  components: {
    PostListComponentVue,
    InputFieldComponentVue,
    ButtonComponentVue,
  },
}
</script>

<style scoped>
</style>
