<template>
  <div>
    <div
      class="vh-100 d-flex flex-column justify-content-center align-items-center p-4 p-md-5 mb-4"
    >
      <div class="home-title fw-bold">
        &lpar;<span class="b-highlight">B</span>&rpar;log
      </div>
      <nuxt-link to="/posts" class="posts-link lead fw-bold"
        >Go To Posts</nuxt-link
      >
    </div>
  </div>
</template>

<script setup></script>

<style scoped>
.posts-link {
  background: linear-gradient(90deg, #ff8303, #ffe000, #ff8303);
  -webkit-background-clip: text;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

.home-title {
  font-size: 5.5rem;
}
</style>
