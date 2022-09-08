<template>
  <div>
    <main class="container">
      <div class="p-4 p-md-5 mb-4 rounded main-b-post">
        <div class="col-md-6 px-0">
          <h1 class="display-4 fst-italic">
            Title of a longer featured blog post
          </h1>
          <p class="lead my-3">
            Multiple lines of text that form the lede, informing new readers
            quickly and efficiently about whats most interesting in this post’s
            contents.
          </p>
          <p class="lead mb-0">
            <a href="#" class="fw-bold">Continue reading...</a>
          </p>
        </div>
      </div>

      <div class="row d-flex mb-2">
        <div class="col-md-6" v-for="post in posts" :key="post.id">
          <Post :post="post" />
        </div>
      </div>
    </main>
  </div>
</template>

<script setup>
const posts = useState('posts', () => []);
const config = {
  headers: { Accept: 'application/json' },
};

try {
  const { data: postsAll } = await useFetch(
    'https://62fe137ba85c52ee482f275b.mockapi.io/api/v1/posts',
    config
  );

  posts.value = postsAll;
} catch (err) {
  console.log(err);
}
</script>

<style scoped>
.blog-post {
  margin-bottom: 4rem;
}
.blog-post-title {
  font-size: 2.5rem;
}
.blog-post-meta {
  margin-bottom: 1.25rem;
  color: #727272;
}
</style>
