<template>
  <button class="carousel-button" @click="$emit('click')">
    <slot></slot>
  </button>
</template>

<script>
export default {
  name: 'Button'
}
</script>

<style scoped>
.carousel-button {
  background: rgba(0, 0, 0, 0.5);
  color: white;
  border: none;
  padding: 10px 15px;
  cursor: pointer;
  z-index: 10;
  /* Örnek stil */
}
</style>