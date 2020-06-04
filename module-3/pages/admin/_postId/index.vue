<template>
  <div class="admin-post-page">
    <section class="update-form">
      <admin-post-form :post="loadedPost"></admin-post-form>
    </section>
  </div>
</template>

<script>
import AdminPostForm from "@/components/Admin/AdminPostForm";

export default {
  data() {
    return {
      loadedPost: {
        author: "Bilbo Baggins",
        title: "The Hobbit",
        content: "In a hole in the ground there lived a hobbit",
        thumbnailLink:
          "https://apod.nasa.gov/apod/image/2004/ISS002-E-7377_1024c.jpg"
      }
    };
  },
  components: {
    AdminPostForm
  },
  layout: 'admin'
};
</script>

<style scoped>
.update-form {
  width: 90%;
  margin: 20px auto;
}
@media (min-width: 768px) {
  .update-form {
    width: 500px;
  }
}
</style>
