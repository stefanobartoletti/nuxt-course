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
export default {
  asyncData(context, callback) {
    setTimeout(() => {
      callback(null, {
        loadedPost: {
          id: '1',
          title: 'The Hobbit (ID: ' + context.route.params.id + ' )',
          author: 'J.R.R. Tolkien',
          updatedDate: new Date(),
          thumbnail:
            'https://kbimages1-a.akamaihd.net/1db01021-c0ce-4afc-93fe-3030acdf86df/353/569/90/False/the-hobbit-3.jpg',
          previewText: 'An unexpected party',
          content:
            'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Omnis recusandae laborum ut minima nam dolorum quis provident, iste officia reprehenderit ad tempore quam ducimus vitae esse aliquid, natus dolorem quidem!'
        }
      });
    }, 1000);
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
