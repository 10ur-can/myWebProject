<template>
  <button
    @click="$emit('click')"
    :class="{ active: isActive }"
    class="carousel-dot"
    :aria-label="'Slayt ' + (index + 1) + 'a git'"
  ></button>
</template>

<script>
export default {
  name: 'AtomDot',
  props: {
    isActive: {
      type: Boolean,
      default: false
    },
    index: {
      type: Number,
      required: true
    }
  }
}
</script>

<style scoped>
.carousel-dot {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background-color: #ccc;
  border: none;
  margin: 0 5px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.carousel-dot.active {
  background-color: #333;
}
</style>