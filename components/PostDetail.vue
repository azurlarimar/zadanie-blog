<template>
  <div>
    <main class="container">
      <div class="row mb-2">
        <div class="col">
          <h2>{{ post.title }}</h2>
          <div class="mb-4 text-muted">{{ truncatedDate }}</div>
          <p class="fs-5 mb-5">{{ post.content }}</p>
          <div class="d-flex justify-content-center mb-5">
            <img class="rounded img-fluid" :src="post.image" alt="post-image" />
          </div>
          <hr />

          <div class="row g-4 mb-2">
            <div v-for="comment in comments" :key="comment.id">
              <Comment :comment="comment" />
            </div>
          </div>
        </div>
      </div>
    </main>
  </div>
</template>

<script setup>
import { truncateDate } from '../utils/truncateStrings';

const post = useState('post', () => []);
const comments = useState('comments', () => []);
const route = useRoute();

const postConfig = {
  headers: { Accept: 'application/json' },
  key: route.params.id,
};

const commentConfig = {
  headers: { Accept: 'application/json' },
};

try {
  const { data: postDetail } = await useFetch(
    `https://62fe137ba85c52ee482f275b.mockapi.io/api/v1/posts/${route.params.id}`,
    postConfig
  );

  post.value = postDetail;
} catch (err) {
  console.log(err);
}

try {
  const { data: comment } = await useFetch(
    `https://62fe137ba85c52ee482f275b.mockapi.io/api/v1/comments`,
    commentConfig
  );

  comments.value = comment;
} catch (err) {
  console.log(err);
}

const truncatedDate = computed(() => {
  return truncateDate(post.value.createdAt, 10);
});
</script>

<style></style>
