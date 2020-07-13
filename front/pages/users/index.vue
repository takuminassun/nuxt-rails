<template>
  <div>
    <ul>
      <li v-for="user in users" :key="user.name">
        {{ user.name }}
      </li>
    </ul>
    <router-link to="/users/new">新規登録</router-link>
  </div>
</template>

<script>
export default {
  asyncData({ $axios }) {
    return $axios.$get(`/api/users/`)
      .then((res) => {
        return { users: res }
      })
  }
}
</script>

<style lang="stylus" scoped>

</style>
