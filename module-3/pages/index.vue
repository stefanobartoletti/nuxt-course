<template>
  <div class="home-page">
    <section class="intro">
      <h1>Get the latest tech news</h1>
    </section>
    <post-list :posts="loadedPosts"></post-list>
  </div>
</template>

<script>
import PostList from "~/components/Post/PostList";

export default {
  // data() {
  //   return {
  //     loadedPosts: []
  //   };
  // },
  asyncData(context, callback) {
    setTimeout(() => {
      callback(null, {
        loadedPosts: [
          {
            id: "1",
            title: "The Hobbit",
            thumbnail:
              "https://kbimages1-a.akamaihd.net/1db01021-c0ce-4afc-93fe-3030acdf86df/353/569/90/False/the-hobbit-3.jpg",
            previewText: "An unexpected party"
          },
          {
            id: "2",
            title: "The Lord of the Rings",
            thumbnail:
              "https://kbimages1-a.akamaihd.net/92525c4a-613e-492d-ad9f-44d646c14d8c/353/569/90/False/the-fellowship-of-the-ring.jpg",
            previewText: "A long expected party"
          },
          {
            id: "3",
            title: "The Silmarillion",
            thumbnail:
              "https://kbimages1-a.akamaihd.net/af1f059d-c5db-496b-9650-ad702bb389af/353/569/90/False/the-silmarillion-1.jpg",
            previewText: "The Valaquenta"
          },
          {
            id: "4",
            title: "Unfinished Tales",
            thumbnail: "",
            previewText: "of Numenor and Middle-earth"
          }
        ]
      });
    }, 1500);
  },
  components: {
    PostList
  },
  created() {}
};
</script>

<style scoped>
.intro {
  height: 300px;
  position: relative;
  padding: 30px;
  box-sizing: border-box;
  background-image: url("~assets/img/main-page-background.jpg");
  background-position: center;
  background-size: cover;
}

.intro h1 {
  position: absolute;
  top: 10%;
  left: 5%;
  width: 90%;
  font-size: 1.5rem;
  color: black;
  background-color: rgb(211, 211, 211);
  padding: 10px;
  border-radius: 10px;
  box-shadow: 3px 3px 3px black;
  box-sizing: border-box;
  border: 1px solid black;
}

@media (min-width: 768px) {
  .intro h1 {
    font-size: 2rem;
  }
}
</style>
