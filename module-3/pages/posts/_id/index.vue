<template>
  <div class="single-post-page">
    <section class="post">
      <h1 class="post-title">{{ loadedPost.title }}</h1>
      <div class="post-details">
        <p class="post-detail">Posted on {{ loadedPost.updatedDate }}</p>
        <p class="post-detail">Written by {{ loadedPost.author }}</p>
      </div>
      <div>{{ loadedPost.content }}</div>
    </section>
    <section class="post-feedback">
      <p>
        Write a mail to
        <a href="mailto:test@example.com">test@example.com</a>.
      </p>
    </section>
  </div>
</template>

<script>
import axios from 'axios';

export default {
  asyncData(context) {
    return axios
      .get(
        'https://sb-nuxt-blog.firebaseio.com/posts/' +
          context.params.id +
          '.json'
      )
      .then(res => {
        return {
          loadedPost: res.data,
        }
      })
      .catch(e => context.error(e));
  }
};
</script>

<style>
.single-post-page {
  padding: 30px;
  text-align: center;
  box-sizing: border-box;
}

.post {
  width: 100%;
}

@media (min-width: 768px) {
  .post {
    width: 600px;
    margin: auto;
  }
}

.post-title {
  margin: 0;
}

.post-details {
  padding: 10px;
  box-sizing: border-box;
  border-bottom: 3px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

@media (min-width: 768px) {
  .post-details {
    flex-direction: row;
  }
}

.post-detail {
  color: rgb(88, 88, 88);
  margin: 0 10px;
}

.post-feedback a {
  color: red;
  text-decoration: none;
}

.post-feedback a:hover,
.post-feedback a:active {
  color: salmon;
}
</style>
