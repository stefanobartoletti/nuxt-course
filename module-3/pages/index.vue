<template>
  <div class="home-page">
    <section class="intro">
      <h1>Get the latest tech news</h1>
    </section>
    <section class="featured-posts">
      <post-preview
        id="1"
        title="Post 1 Title"
        thumbnail="https://apod.nasa.gov/apod/image/2004/ISS002-E-7377_1024c.jpg"
        previewText="Lorem ipsum post 1"
      />
      <post-preview
        id="2"
        title="Post 2 Title"
        thumbnail="https://apod.nasa.gov/apod/image/2004/ISS002-E-7377_1024c.jpg"
        previewText="Lorem ipsum post 2"
      />
      <post-preview
        id="3"
        title="Post 3 Title"
        thumbnail="https://apod.nasa.gov/apod/image/2004/ISS002-E-7377_1024c.jpg"
        previewText="Lorem ipsum post 3"
      />
    </section>
  </div>
</template>

<script>
import PostPreview from "~/components/Post/PostPreview";

export default {
  components: {
    PostPreview
  }
};
</script>

<style scoped>
.intro {
  height: 300px;
  position: relative;
  padding: 30px;
  box-sizing: border-box;
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

.featured-posts {
  display: flex;
  padding: 20px;
  box-sizing: border-box;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
</style>
