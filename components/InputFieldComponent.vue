<template>
  <input :value="input" @input="$emit('value', input)" class="input" type="text">
</template>

<script>

export default {
  name: 'input-field',
  data() {
    return {
      input: ''
    }
  },
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
