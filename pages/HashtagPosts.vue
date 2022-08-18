<template>
  <div>
    <form @submit.prevent>
      <InputFieldComponentVue @input-string="hashtag = $event" />
      <ButtonComponent />
    </form>
    <h1>Посты по хештегам</h1>

    <PostListComponentVue :posts="postsByHashtag" />
  </div>
</template>

<script>
import InputFieldComponentVue from '~/components/InputFieldComponent.vue';
import ButtonComponentVue from '~/components/ButtonComponent.vue';
import PostListComponentVue from '~/components/PostListComponent.vue';
import ButtonComponent from '~/components/ButtonComponent.vue';

export default {
  /* async asyncData({ hashtag, $axios }) {
    const postsByHashtag = await $axios.$get('getpostsbyhashtag/' + hashtag);
    return { postsByHashtag };
  }, */
  data() {
    return {
      hashtag: '',
      posts: ''
    }
  },
  methods: {
    findPosts() {
      this.$axios.$get('getpostsbyhashtag/' + this.hashtag).then(response => this.posts = response.data);
    }
  },
  components: {
    PostListComponentVue,
    InputFieldComponentVue,
    ButtonComponentVue,
    ButtonComponent
  },
}
</script>

<style scoped>
</style>
