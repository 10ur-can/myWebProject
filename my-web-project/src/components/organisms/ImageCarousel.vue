<template>
  <div class="image-carousel">
    <Button class="prev-button" @click="prevImage">
      &lt;
    </Button>

    <div class="carousel-content">
      <CarouselItem
        v-for="(image, index) in images"
        :key="index"
        :image="image"
        :is-active="currentIndex === index"
      />
    </div>

   <Button class="next-button" @click="nextImage">
      &gt;
    </Button>

    <div class="carousel-indicators">
      <span
        v-for="(image, index) in images"
        :key="'dot-' + index"
        class="dot"
        :class="{ 'is-active': currentIndex === index }"
        @click="goToImage(index)"
      ></span>
    </div>

  </div>
</template>

<script>
import CarouselItem from '@/components/molecules/carouselItem.vue'; // Yolunuzu düzenleyin
import Button from '@/components/atoms/button.vue'; // Yolunuzu düzenleyin

export default {
  name: 'ImageCarousel',
  components: {
    CarouselItem,
    Button
  },
  props: {
    images: {
      type: Array,
      required: true,
      validator: (arr) => arr.length === 4
    }
  },
  data() {
    return {
      currentIndex: 0
    };
  },
  methods: {
    nextImage() {
     this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    prevImage() {
      this.currentIndex = (this.currentIndex - 1 + this.images.length) % this.images.length;
    },
    goToImage(index) {
      this.currentIndex = index;
    }
  }
}
</script>

<style scoped>
.image-carousel {
  position: relative;
  width:100%; /* Boyut örneği */
  margin: 0 auto;
  background-image:center;
}

.carousel-content {
  position: relative;
  overflow: hidden; /* Carousel item'larını gizlemek için */
  height: 600px; /* Sabit bir yükseklik belirleyin */
}

/* Navigasyon düğmeleri için konumlandırma */
.prev-button, .next-button {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  border-radius: 50%;
  padding: 10px;
}

.prev-button { left: 10px; }
.next-button { right: 10px; }

/* Gösterge noktaları */
.carousel-indicators {
  text-align: center;
  margin-top: 10px;
}

.dot {
  display: inline-block;
  width: 10px;
  height: 10px;
  margin: 0 5px;
  background: #ccc;
  border-radius: 50%;
  cursor: pointer;
  transition: background 0.3s;
}

.dot.is-active {
  background: #333;
}
</style>