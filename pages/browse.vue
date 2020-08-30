<template>
  <div class="flex font-main container mx-auto">
    <div class="sidebar w-2/12 border-r relative">
      <Categories :categories="categories" @changeCategory="changeCategory" />
    </div>
    <div class="main w-10/12 px-8">
      <div>
        <p class="uppercase tracking-widest text-gray-900 text-lg font-semibold">Handpicked</p>
      </div>
      <div class="books mt-12">
        <Books :category="pickedCategory" />
      </div>
    </div>
  </div>
</template>
<script>
import Categories from "@/components/Categories";
import Books from "@/components/Books";
export default {
  components: {
    Categories,
    Books,
  },
  data() {
    return {
      categories: [],
      pickedCategory: "",
    };
  },
  methods: {
    changeCategory(value) {
      this.pickedCategory = value;
    },
  },
  async asyncData({ app, params }) {
    let { data } = await app.$axios.$get("categories");
    return {
      categories: data,
    };
  },
};
</script>
