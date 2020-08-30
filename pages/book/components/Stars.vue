<template>
  <div class="flex items-end">
    <div class="stars flex mr-3">
      <client-only>
        <star-rating
          :rating="rating.avg"
          :read-only="true"
          :star-size="18"
          :show-rating="false"
          active-color="#ed8936"
        ></star-rating>
      </client-only>
    </div>
    <div class="overall mr-3">
      <p class="text-read-empress text-sm">4.04</p>
    </div>
    <div class="rating mr-3">
      <p class="text-orange-500 underline text-sm">Rating details</p>
    </div>
    <div class="rating-details mr-3">
      <p class="text-orange-500 underline text-sm">
        {{ rating.rating_total }} Ratings
      </p>
    </div>
    <div class="review">
      <p class="text-orange-500 underline text-sm">
        {{ rating.review_total }} Reviews
      </p>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    rating: {
      type: Object,
      require: true
    }
  }
};
</script>
