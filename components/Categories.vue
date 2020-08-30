<template>
  <div>
    <div class="flex flex-col">
      <a href class="text-base font-light text-gray-600 mb-4">Books That We Love</a>
      <a href class="text-base font-light text-gray-600 mb-4">Handpicked</a>
      <a href class="text-base font-light text-gray-600 mb-4">Latest Releases</a>
    </div>
    <div class="categries mt-6">
      <p class="uppercase tracking-widest text-gray-800">Categories</p>
      <div class="mt-3 flex flex-col">
        <a
          href="#"
          @click.prevent="changeCategory(category.slug)"
          class="text-sm font-light text-gray-600 mb-2"
          v-for="category in categories"
          :key="category.slug"
        >{{category.title}}</a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    categories: {
      type: Array,
      required: true,
    },
  },
  methods: {
    changeCategory(slug) {
      this.$emit("changeCategory", slug);
    },
  },
};
</script>
