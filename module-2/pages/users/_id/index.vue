<template>
  <div class="container">
    <h1 class="title">A single user with ID: {{ $route.params.id }}</h1>
  </div>
</template>

<script>
export default {
  validate (data) { // validate() is a Nuxt native method to validate data
    // return data.params.id == 1;
    return /^\d+$/.test(data.params.id) // acccess this page only of the id is a number
  }
};
</script>

<style></style>
