<template>
  <div class="grid grid-cols-5 gap-12">
    <div v-for="book in books" :key="book.id">
      <img src="@/static/images/book11.png" class="w-full rounded-lg" alt />
      <p class="text-sm text-gray-800 mt-3 mb-1 tracking-wide">
        {{ book.title }}
      </p>
      <p class="text-xs text-gray-500 tracking-wide">
        {{ book.authors[0].first_name }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    books: {
      required: true,
      type: Array
    }
  }
};
</script>
