<template>
  <div>
    <comp-header></comp-header>
    <nuxt />
  </div>
</template>

<script>
import compHeader from '~/components/Header.vue'

export default {
  components: {
    compHeader,
  }
}
</script>

<style>

</style>
