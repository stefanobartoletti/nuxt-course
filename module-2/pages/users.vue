<template>
    <div class="container">
    <h1 class="title">The users view</h1>
    <div>
      <input type="text" v-model="userID">
      <button @click="onLoadUser">Load User</button>
      <nuxt-child></nuxt-child>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      userID: ''
    }
  },
  methods: {
    onLoadUser() {
      this.$router.push('/users/' + this.userID)
    }
  },
  layout: 'users',
};
</script>

<style scoped>
.container {
  flex-direction: column;
}

</style>