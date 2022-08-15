<template>
  <form @submit.prevent>
    <input v-model="inputFieldString" class="input" type="text" placeholder="Название хештега">
    <button class="btn" @click="customFunction">Жмякай</button>
  </form>
</template>

<script>

export default {
  data() {
    return {
      inputFieldString: '',
    }
  },
  props: {
    customFunction: {
      type: Function,
      required: true
    }
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
</style>
