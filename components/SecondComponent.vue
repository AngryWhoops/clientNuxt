<template>
  <div>
    <input type="text" :value="modelValue" @input="updateValue($event.target.value)" >
  </div>
</template>

<script>
export default {
  name: "SecondComponent",
  props: {
    modelValue: {
      type: [String, Number],
      default: ''
    }
  },
  emits: ['update:modelValue', 'change'],
  model: {
    prop: 'modelValue',
    event: 'update:modelValue'
  },
  data() {
    return {
    }
  },
  /*computed: {
    changeInput: {
      get() {
        return this.localValue;
      },
      set(value)
      {
          this.$emit('update', value);
      }
    }
  },*/
  methods: {
    /*
    *UpdateModelValue совпадает с настроенной моделью
    */
    updateValue(value) {
      this.$emit('update:modelValue', value);
    },
    onChange(e) {
      this.$emit('change', this.modelValue, e);
    }
  }
}
</script>

<style scoped>

</style>
