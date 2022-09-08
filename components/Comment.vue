<template>
  <div>
    <div class="row">
      <div class="col-2 col-md-1">
        <img
          :src="comment.avatar"
          alt="avatar"
          class="avatar align-middle rounded-circle"
        />
      </div>
      <div class="col-8 col-md-10">
        <span class="me-2 fw-bold">{{ comment.name }}</span>
        <span>{{ comment.comment }}</span>
        <div class="mt-2 text-muted comment-date">{{ truncatedDate }}</div>
        <hr class="text-muted" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { truncateDate } from '../utils/truncateStrings';

const props = defineProps({
  comment: Object,
});

const { comment } = toRefs(props);

const truncatedDate = computed(() => {
  return truncateDate(comment.value.createdAt, 10);
});
</script>

<style scoped>
.avatar {
  width: 50px;
  height: 50px;
}
.comment-date {
  font-size: 14px;
}
</style>
