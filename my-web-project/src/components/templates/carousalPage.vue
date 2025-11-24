<template>
  <div class="home-page">
    <ImageCarousel :images="carouselImages" class="carouselimage" />
  </div>
</template>

<script>
import ImageCarousel from '@/components/organisms/ImageCarousel.vue'; // Yolunuzu düzenleyin
import image1 from '@/assets/images/carouselimage1.webp'
import image2 from '@/assets/images/carouselimage2.jpg'
import image3 from '@/assets/images/carousalimage5.jpeg'
import image4 from '@/assets/images/carouselimage4.webp'

export default {
  name: 'HomePage',
  components: {
    ImageCarousel
  },
  data() {
    return {
      carouselImages: [
        { src: image1, alt: 'Resim 1' },
        { src: image2, alt: 'Resim 2' },
        { src: image3, alt: 'Resim 3' },
        { src: image4, alt: 'Resim 4' }
      ]
    };
  }
}
</script>

<style scoped>
.home-page {
  text-align: center;
}
</style>