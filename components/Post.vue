<template>
  <div>
    <nuxt-link :to="`/posts/post/${post.id}`" class="card-link">
      <div
        class="row g-0 border border-3 border-light border-colorful rounded overflow-hidden flex-md-row mb-4 shadow-sm h-md-250 position-relative"
      >
        <div class="col-lg-7 p-3 d-flex flex-column position-static h-100">
          <strong class="d-inline-block mb-2 text-primary">{{
            post.slug
          }}</strong>
          <h3 class="mb-0">{{ post.title }}</h3>
          <div class="mb-1 text-muted">{{ truncatedDate }}</div>
          <p class="card-text mb-auto content-wrap">
            {{ truncatedContent }}
          </p>
        </div>
        <div class="col-5 d-none d-lg-block h-100 m-0">
          <img :src="post.image" alt="post-thumbnail" class="h-100" />
        </div>
      </div>
    </nuxt-link>
  </div>
</template>

<script setup>
import { truncateString, truncateDate } from '../utils/truncateStrings.js';

const props = defineProps({
  post: Object,
});
const { post } = toRefs(props);

const truncatedContent = computed(() => {
  return truncateString(post.value.content, 130);
});

const truncatedDate = computed(() => {
  return truncateDate(post.value.createdAt, 10);
});
</script>
