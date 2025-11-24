<template>
  <div class="category-slider-container">
    <h2>Öne Çıkan Kategoriler</h2>
    
    <div class="slider-wrapper" ref="sliderWrapper">
      <div v-for="category in categories" :key="category.id" class="category-card">
        <div class="image-wrapper">
          <img :src="category.image" :alt="category.name">
        </div>
        <div class="category-name">
          {{ category.name }}
        </div>
      </div>
    </div>
    
    <div class="slider-footer-controls">
      <button @click="scrollLeft" class="scroll-button left-button">
        &#10094; </button>
      
      <div class="dots-placeholder">
        </div>
      
      <button @click="scrollRight" class="scroll-button right-button">
        &#10095; </button>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import image from '@/assets/images/kategoriimage.webp'

// Kaydırma alanına erişmek için ref
const sliderWrapper = ref(null);
// Bir tıklandığında ne kadar kaydırılacağını belirler
const SCROLL_DISTANCE = 430; 

// Sola Kaydırma Metodu
const scrollLeft = () => {
  if (sliderWrapper.value) {
    sliderWrapper.value.scrollBy({
      left: -SCROLL_DISTANCE,
      behavior: 'smooth'
    });
  }
};

// Sağa Kaydırma Metodu
const scrollRight = () => {
  if (sliderWrapper.value) {
    sliderWrapper.value.scrollBy({
      left: SCROLL_DISTANCE,
      behavior: 'smooth'
    });
  }
};

const categories = ref([
  { id: 1, name: 'Öğretmenler Günü Hediyesi', image },
  { id: 2, name: 'Sepette %20 İndirim', image },
  { id: 3, name: 'Gömlek',  image },
  { id: 4, name: 'Mont & Kaban', image },
  { id: 5, name: 'Pantolon', image },
  { id: 6, name: 'Aksesuarlar', image},
]);
</script>

---

<style scoped>
/*
  CSS Kodları (Yeni Ayaklık Kontrolleri İçin Güncellemeler)
*/

.category-slider-container {
  padding: 20px 0;
  max-width: 1200px;
  margin: 0 auto;
}

h2 {
  text-align: center;
  margin-bottom: 20px;
  font-size: 2em;
  font-weight: 500;
}

/* Kaydırma alanının temel stili (Değişmedi) */
.slider-wrapper {
  display: flex; 
  overflow-x: auto;
  -webkit-overflow-scrolling: touch;
  padding-bottom: 15px; 
  scroll-behavior: smooth;
  
  /* Scrollbar'ı gizle (Tercihe bağlı) */
  scrollbar-width: none;
  -ms-overflow-style: none;
}
.slider-wrapper::-webkit-scrollbar {
  display: none; 
}

/* Yeni Buton Kontrol Alanı */
.slider-footer-controls {
  display: flex; /* Öğeleri yan yana dizer */
  justify-content: space-between; /* Sol ve sağ butonları kenarlara yayar */
  align-items: center;
  margin-top: 10px; /* Kaydırma alanından biraz aşağıda boşluk bırakır */
  padding: 0 10px;
}

.scroll-button {
  /* Butonların dairesel ve sade stili */
  background: none; /* Arka planı kaldır */
  color: #333;
  border: 1px solid #ccc;
  border-radius: 50%;
  width: 35px; /* Daha küçük butonlar */
  height: 35px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  font-size: 1.2em;
  font-weight: bold;
  transition: background-color 0.2s;
}

.scroll-button:hover {
  background-color: #f0f0f0;
}

/* Kategori kart stilleri (Aynı kaldı) */
.category-card {
  flex-shrink: 0; 
  width: 200px; 
  margin-right: 15px; 
  text-align: center;
  cursor: pointer;
  transition: transform 0.3s ease;
}

.category-card:hover {
  transform: translateY(-5px);
}

.image-wrapper {
  width: 100%;
  height: 270px; 
  overflow: hidden;
}

.image-wrapper img {
  width: 100%;
  height: 100%;
  object-fit: cover; 
  display: block;
}

.category-name {
  margin-top: 8px;
  font-size: 1.1em;
  font-weight: 600;
  color: #333;
}
</style>