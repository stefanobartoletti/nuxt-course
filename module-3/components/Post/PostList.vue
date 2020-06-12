<template>
  <section class="post-list">
    <post-preview
      v-for="post in posts"
      :key="post.id"
      :is-admin="isAdmin"
      :id="post.id"
      :title="post.title"
      :thumbnail="post.thumbnail"
      :previewText="post.previewText"
    />
  </section>
</template>

<script>
import PostPreview from '~/components/Post/PostPreview';

export default {
  props: {
    isAdmin: {
      type: Boolean,
      default: false
    },
    posts: {
      type: Array,
      required: true
    }
  },
  components: {
    PostPreview
  }
};
</script>

<style scoped>
.post-list {
  display: flex;
  padding: 20px;
  box-sizing: border-box;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
</style>
