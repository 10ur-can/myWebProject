<template>
  <div class="carousel-item" :class="{ 'is-active': isActive }">
    <Image :src="image.src" :alt="image.alt" />
  </div>
</template>

<script>
import Image from '@/components/atoms/Image.vue'; // Yolunuzu düzenleyin

export default {
  name: 'CarouselItem',
  components: {
    Image
  },
  props: {
    image: {
      type: Object,
      required: true
    },
    isActive: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped>
.carousel-item {
  min-width: 100%;
  transition: opacity 0.5s ease;
  opacity: 0;
  position: absolute; /* Organizma içinde konumlandırma için */
  top: 0;
  left: 0;
}

.carousel-item.is-active {
  opacity: 1;
  position: relative; /* Aktif olanı görünür yapmak için */
}
</style>