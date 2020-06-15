<template>
  <div class="admin-post-page">
    <section class="update-form">
      <admin-post-form :post="loadedPost" @submit="onSubmitted"></admin-post-form>
    </section>
  </div>
</template>

<script>
import AdminPostForm from '@/components/Admin/AdminPostForm';
import axios from 'axios';

export default {
  asyncData(context) {
    return axios
      .get(
        'https://sb-nuxt-blog.firebaseio.com/posts/' +
          context.params.postId +
          '.json'
      )
      .then(res => {
        return {
          loadedPost: res.data
        };
      })
      .catch(e => context.error(e));
  },
  components: {
    AdminPostForm
  },
  methods: {
    onSubmitted(editedPost) {
      axios
        .put('https://sb-nuxt-blog.firebaseio.com/posts/' +
          this.$route.params.postId +
          '.json', editedPost)
        .then(res => {
          this.$router.push('/admin')
          console.log(res)})
        .catch(e => console.log(e));
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
