<template>
  <div>
    <second-component v-model="localVar"/>
  </div>

</template>

<script>
import SecondComponent from "~/components/SecondComponent";
export default {
  data() {
    return {
        localVar: 'Jopa'
    }
  },
  components: {
    SecondComponent
  }
}
</script>

<style scoped>
</style>
