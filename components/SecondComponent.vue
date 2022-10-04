<template>
  <div>
    <input type="text" v-model="changeInput">
  </div>
</template>

<script>
export default {
  name: "SecondComponent",
  props: {
    inputValue: {
      type: [String, Number],
      default: ''
    }
  },
  model: {
    prop: 'inputValue',
    event: 'update'
  },
  data() {
    return {
      localValue: this.inputValue
    }
  },
  computed: {
    changeInput: {
      get() {
        return this.localValue;
      },
      set(value)
      {
          this.$emit('update', value);
      }
    }
  },
}
</script>

<style scoped>

</style>
