<template>
  <section class="post-list">
    <post-preview
      id="1"
      :is-admin="isAdmin"
      title="Post 1 Title"
      thumbnail="https://apod.nasa.gov/apod/image/2004/ISS002-E-7377_1024c.jpg"
      previewText="Lorem ipsum post 1"
    />
    <post-preview
      id="2"
      :is-admin="isAdmin"
      title="Post 2 Title"
      thumbnail="https://apod.nasa.gov/apod/image/2004/ISS002-E-7377_1024c.jpg"
      previewText="Lorem ipsum post 2"
    />
    <post-preview
      id="3"
      :is-admin="isAdmin"
      title="Post 3 Title"
      thumbnail="https://apod.nasa.gov/apod/image/2004/ISS002-E-7377_1024c.jpg"
      previewText="Lorem ipsum post 3"
    />
  </section>
</template>

<script>
import PostPreview from "~/components/Post/PostPreview";

export default {
  props: {
    isAdmin: {
      type: Boolean,
      default: false
    },
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
