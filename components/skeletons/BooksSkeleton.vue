<template>
  <div class="grid grid-cols-5 gap-12">
    <div
      v-for="(n, index) in 20"
      :key="index"
      class="animate-pulse"
      :style="animationDelay(index)"
    >
      <div class="w-full rounded-lg h-56 bg-gray-300" alt></div>
      <div class="bg-gray-300 h-4 mt-3 mb-1 rounded"></div>
      <div class="bg-gray-300 h-4 mt-3 mb-1 rounded"></div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      delay: 50
    };
  },
  methods: {
    animationDelay(index) {
      return {
        animationFillMode: "backwards",
        animationDelay: this.delay * index + "ms"
      };
    }
  }
};
</script>
