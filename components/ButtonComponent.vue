<template>
  <button class="btn">
    <slot></slot>
  </button>
</template>

<script>

export default {
  name: 'button-component',
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
