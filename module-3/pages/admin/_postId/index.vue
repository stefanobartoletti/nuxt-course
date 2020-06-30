<template>
  <div class="admin-post-page">
    <section class="update-form">
      <admin-post-form :post="loadedPost" @submit="onSubmitted"></admin-post-form>
    </section>
  </div>
</template>

<script>
import AdminPostForm from '@/components/Admin/AdminPostForm';

export default {
  asyncData(context) {
    return context.app.$axios.$get(
        '/posts/' +
        context.params.postId +
        '.json'
      )
      .then(data => {
        return {
          loadedPost: { ...data, id: context.params.postId }
        };
      })
      .catch(e => context.error(e));
  },
  components: {
    AdminPostForm
  },
  methods: {
    onSubmitted(editedPost) {
      this.$store.dispatch('editPost', editedPost).then(() => {
        this.$router.push('/admin');
      });
    }
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
