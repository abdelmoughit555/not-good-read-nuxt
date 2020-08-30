<template>
  <div>
    <div class="comment flex mt-6" v-for="reply in replies" :key="reply.id">
      <div class="w-1/12">
        <img src="@/static/images/user.png" alt />
      </div>
      <div class="w-11/12 -ml-8">
        <div class="flex justify-between items-center">
          <div class="flex items-center">
            <p class="mr-2">
              <span
                class="text-gray-900 capitalize italic font-medium text-sm"
              >{{ reply.user.name }}</span>
            </p>
          </div>
          <div>
            <p class="text-read-empress">Nov 15, 2015</p>
          </div>
        </div>
        <p class="mt-3 text-gray-700 text-sm">{{ reply.text }}</p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    repliesCount: {
      type: [Number, null],
      default: null,
    },
    commentId: {
      type: Number,
      required: true,
    },
  },
  data() {
    return {
      replies: [],
    };
  },
  async fetch() {
    const { data } = await this.$axios.$get(
      `replies/comments/${this.commentId}`
    );
    this.replies = data;
  },
};
</script>
