<template>
  <img :src="src" :alt="alt" class="carousel-image">
</template>

<script>
export default {
  name: 'Image',
  props: {
    src: {
      type: String,
      required: true
    },
    alt: {
      type: String,
      default: 'Carousel Image'
    }
  }
}
</script>

<style scoped>
.carousel-image {
  width: 100%;
  height:auto;
  display: block;
}
</style>