<template>
  <div class="container">
    <h1 class="title">The users view</h1>
    <div>
      <input type="text" v-model="userID">
      <button @click="onLoadUser">Load User</button>
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
};
</script>

<style></style>
