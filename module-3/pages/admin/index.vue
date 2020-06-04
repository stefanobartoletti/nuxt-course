<template>
  <div class="admin-page">
      <section class="new-post">
          <app-button @click="$router.push('/admin/new-post')">Create new post</app-button>
      </section>
      <section class="existing-posts">
          <h1>Existing posts</h1>
          <post-list isAdmin ></post-list>
      </section>
  </div>
</template>

<script>
import PostList from '@/components/Post/PostList'
import AppButton from '@/components/UI/AppButton'

export default {
components: {
    AppButton,
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