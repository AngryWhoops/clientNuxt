<template>
  <div>
    <div class="post-item" v-bind="post">
      <div class="datefield">
        Создан: {{ post.created_at }} | Автор: {{ post.user.login }}
      </div>
      <div>{{ post.body }}</div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.post-item {
  padding: 10px 10px;
  border: 3px solid teal;
  border-radius: 6px;
  margin: 10px 10px 10px;
}

.datefield {
  font-size: 15px;
  color: dimgray;
}
</style>
