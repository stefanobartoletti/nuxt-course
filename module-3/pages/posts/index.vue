<template>
  <div class="posts-page">
    <post-list :posts="loadedPosts"></post-list>
  </div>
</template>

<script>
import PostList from '~/components/Post/PostList';

export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          loadedPosts: [
            {
              id: '1',
              title: 'The Hobbit',
              thumbnail:
                'https://kbimages1-a.akamaihd.net/1db01021-c0ce-4afc-93fe-3030acdf86df/353/569/90/False/the-hobbit-3.jpg',
              previewText: 'An unexpected party'
            },
            {
              id: '2',
              title: 'The Lord of the Rings',
              thumbnail:
                'https://kbimages1-a.akamaihd.net/92525c4a-613e-492d-ad9f-44d646c14d8c/353/569/90/False/the-fellowship-of-the-ring.jpg',
              previewText: 'A long expected party'
            },
            {
              id: '3',
              title: 'The Silmarillion',
              thumbnail:
                'https://kbimages1-a.akamaihd.net/af1f059d-c5db-496b-9650-ad702bb389af/353/569/90/False/the-silmarillion-1.jpg',
              previewText: 'The Valaquenta'
            },
            {
              id: '4',
              title: 'Unfinished Tales',
              thumbnail:
                'https://kbimages1-a.akamaihd.net/2305828e-43b9-4985-948a-f6974daf1239/353/569/90/False/unfinished-tales-of-numenor-and-middle-earth.jpg',
              previewText: 'of Numenor and Middle-earth'
            }
          ]
        });
      }, 1000);
      // reject(new Error())
    })
      .then(data => {
        return data;
      })
      .catch(e => {
        context.error(new Error());
      });
  },
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
