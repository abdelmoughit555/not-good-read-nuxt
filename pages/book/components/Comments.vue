<template>
  <div>
    <Comment v-for="comment in comments" :key="comment.id" :comment="comment" />
    <div
      class="w-full rounded-lg bg-read-gray-93 py-4 mt-4"
      v-if="lastPage > page"
      @click="loadMore"
    >
      <template v-if="$fetchState.pending">
        <p class="text-center text-read-empress text-sm">Loading...</p>
      </template>
      <template v-else>
        <p class="text-center text-read-empress text-sm">Load more</p>
      </template>
    </div>
  </div>
</template>
<script>
import Comment from "../components/Comment";

export default {
  components: {
    Comment,
  },
  data() {
    return {
      comments: [],
      page: 1,
      lastPage: 1,
    };
  },
  methods: {
    loadMore() {
      this.page++;
      this.$fetch();
    },
  },
  async fetch() {
    const { data, meta } = await this.$axios.$get(
      `comments/books/${this.page}`
    );
    this.comments.push(...data);
    this.lastPage = meta.last_page;
  },
};
</script>
