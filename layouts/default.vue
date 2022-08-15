<template>
  <div>
    <div class="navigation">
      <NuxtLink class="link" to="/">Лента</NuxtLink>
      <NuxtLink class="link" to="/create">Создать пост</NuxtLink>
      <NuxtLink class="link" to="/hashtagposts">Посты по тегу</NuxtLink>
      <NuxtLink class="link" to="/userposts">Пользовательские посты</NuxtLink>
    </div>
    <Nuxt />
  </div>
</template>

<script>

export default {
  data() {
    return {

    }
  }
}
</script>

<style>
a.nuxt-link-exact-active {
  color: #00c58e;
}

.navigation {
  padding: 30px;
  text-align: center;
  background-color: rgb(48, 48, 48);
}

.link {
  font-size: 20px;
  font-weight: 600;
  color: #ffffff;
  margin-right: 15px;
  text-decoration: none;
  padding: 10px 10px;
  border: 3px solid rgb(104, 104, 104);
  border-radius: 6px;
}

a:hover {
  color: #00c58e;
  border: 3px solid rgb(77, 77, 77);
  background-color: rgb(77, 77, 77);
}
</style>
