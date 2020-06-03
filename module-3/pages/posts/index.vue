<template>
  <div class="posts-page">
    <post-list></post-list>
  </div>
</template>

<script>
import PostList from "~/components/Post/PostList";

export default {    
  components: {
    PostList
  }
};
</script>

<style scoped>
.posts-page {
  display: flex;
  justify-content: center;
  align-items: center;
}


</style>
