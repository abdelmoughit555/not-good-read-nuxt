<template>
  <div class="comment flex mt-6">
    <div class="w-1/12">
      <img src="@/static/images/user.png" alt />
    </div>
    <div class="w-11/12 -ml-8">
      <div class="flex justify-between items-center">
        <div class="flex items-center">
          <p class="mr-2">
            <span
              class="text-gray-900 capitalize italic font-medium text-sm"
            >{{ comment.user.name }}</span>
            <span class="text-gray-800 text-sm">rated it</span>
          </p>
          <client-only>
            <star-rating
              :rating="comment.user.rating"
              :read-only="true"
              :star-size="18"
              :show-rating="false"
              active-color="#ed8936"
            ></star-rating>
          </client-only>
        </div>
        <p class="text-read-empress">{{comment.created_at}}</p>
      </div>
      <p class="mt-3 text-gray-700 text-sm">{{ comment.text }}</p>
      <div class="mt-2 flex items-center">
        <p
          class="text-read-empress flex items-baseline text-sm italic mr-4"
        >{{ comment.likes_count }} Likes</p>
        <template v-if="comment.replies_count">
          <a
            href="#"
            @click.prevent="loadReplies = true"
            class="text-read-empress flex items-baseline text-sm italic"
          >{{comment.replies_count}} replies</a>
        </template>
      </div>
      <Reply :commentId="comment.id" :repliesCount="comment.replies_count" v-if="loadReplies" />
    </div>
  </div>
</template>
<script>
import Reply from "../components/Reply";

export default {
  props: {
    comment: {
      required: true,
      type: Object,
    },
  },
  components: {
    Reply,
  },
  data() {
    return { loadReplies: false };
  },
};
</script>
