<template>
  <div>
    <template v-if="$fetchState.pending">
      <BooksSkeleton />
    </template>
    <template v-else>
      <BooksData :books="books" />
    </template>
  </div>
</template>
<script>
import BooksSkeleton from "./skeletons/BooksSkeleton";
import BooksData from "./data/BooksData";
export default {
  props: {
    category: {
      type: String,
      required: false
    }
  },
  data() {
    return {
      books: []
    };
  },
  components: {
    BooksSkeleton,
    BooksData
  },

  watch: {
    category() {
      this.$fetch();
    }
  },

  async fetch() {
    let { data, meta } = await this.$axios.$get("books", {
      params: {
        category: this.category
      }
    });
    this.books = data;
    this.meta = meta;
  }
};
</script>
