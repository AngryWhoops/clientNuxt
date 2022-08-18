<template>
  <form @submit.prevent>
    <!-- <input v-model="post.body" class="input" type="text" placeholder="Описание">
    <button class="btn" v-if="post.body.length <= 280" @click="createPost">Жмякай</button>
    <div v-else>Текст больше 280 элементов</div> -->

    <input-field-component-vue @value="post.body = value" placeholder="Текст поста" />
    <button-component-vue @click="createPost">Создать</button-component-vue>
  </form>
</template>

<script>
import InputFieldComponentVue from './InputFieldComponent.vue'
import ButtonComponentVue from './ButtonComponent.vue'

export default {
  data() {
    return {
      post: {
        body: '',
      },
    }
  },
  methods: {
    createPost() {
      $axios
        .$post('createmypost', this.post)
        .catch(e => console.log(e.response))

      this.post = {
        body: ''
      }
    }
  },
  components: {
    InputFieldComponentVue,
    ButtonComponentVue
  }
}
</script>

<style scoped>
.input {
  width: 100%;
  height: 25px;
  padding: 10px 10px;
  margin-top: 10px;
}

.btn {
  background-color: teal;
  border-radius: 6px;
  width: 90px;
  color: aliceblue;
}
</style>
