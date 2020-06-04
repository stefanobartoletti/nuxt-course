<template>
  <div class="admin-page">
      <section class="new-post">
          <button @click="$router.push('/admin/new-post')">Create new post</button>
      </section>
      <section class="existing-posts">
          <h1>Existing posts</h1>
          <post-list isAdmin ></post-list>
      </section>
  </div>
</template>

<script>
import PostList from '@/components/Post/PostList'
export default {
components: {
    PostList,
},
}
</script>

<style scoped>
.admin-page {
  padding: 20px;
}

.new-post {
  text-align: center;
  border-bottom: 2px solid #ccc;
  padding-bottom: 10px;
}

.existing-posts h1 {
  text-align: center;
}
</style>