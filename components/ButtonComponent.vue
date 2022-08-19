<template>
  <button class="btn" @click="$emit('click')">
    <slot></slot>
  </button>
</template>

<script>

export default {
  emits: ['click']
}
</script>
<style scoped>
.btn {
  background-color: teal;
  border-radius: 6px;
  width: 90px;
  color: aliceblue;
}
</style>
