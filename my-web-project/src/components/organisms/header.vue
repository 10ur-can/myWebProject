<template>
  <header class="main-header">
    <div class="header-left">
      <div class="search-box">
        <input type="text" placeholder="Arama: Ceket, Ara" aria-label="Arama Kutusu">
        <button class="search-icon" aria-label="Ara">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" width="20" height="20" fill="currentColor"><path d="M416 208c0 45.9-14.9 88.3-40 122.7L502.6 457.4c12.5 12.5 12.5 32.8 0 45.3s-32.8 12.5-45.3 0L330.7 376c-34.4 25.1-76.8 40-122.7 40C93.1 416 0 322.9 0 208S93.1 0 208 0S416 93.1 416 208zm-116 0c0-64.7-52.7-117-117-117s-117 52.7-117 117s52.7 117 117 117s117-52.7 117-117z"/></svg>
        </button>
      </div>
    </div>

    <div class="header-center">
       <img v-bind:src="imagelogo" class="logo" v-bind:form></img>
    </div>

    <div class="header-right">
      <a href="/login" class="icon-link" aria-label="Giriş Yap/Hesabım">
        <usericon></usericon>
       </a>
      <a href="/wishlist" class="icon-link" aria-label="Favorilerim">
        <kayiticon></kayiticon>
       </a>
      <a href="/cart" class="icon-link cart-link" aria-label="Sepetim">
      </a>
    </div>
  </header>
</template>

<script setup>
 import {ref} from 'vue'
 import image from '@/assets/images/kigililogo.jfif'
 import usericon from '@/components/atoms/a-user-icon.vue'
 import kayiticon from '@/components/atoms/kayiticon.vue'
import form from '@/components/templates/loginpage.vue'

 const imagelogo = ref(image)

</script>


<style scoped>
/* Ana Header Kapsayıcısı: Flexbox ile hizalama */
.main-header {
  display: flex;
  justify-content: space-between; /* Öğeleri uçlara yay */
  align-items: center; /* Dikeyde ortala */
  padding: 10px 40px; /* Kenarlardan biraz boşluk */
  background-color: white;
  border-bottom: 1px solid #eee; /* Alt çizgi */
  height: 70px; /* Belirli bir yükseklik */
}

/* --- SOL KISIM: ARAMA --- */
.header-left {
  flex: 1; /* Alanda yer kaplaması için */
}

.search-box {
  display: flex;
  align-items: center;
  width: 280px; /* Görseldeki gibi dar bir kutu */
  background-color: #f0f0f0; /* Açık gri arkaplan */
  padding: 8px 10px;
  border-radius: 4px;
}

.search-box input[type="text"] {
  flex-grow: 1;
  border: none;
  background: transparent;
  outline: none;
  font-size: 14px;
  color: #333;
}

.search-box input[type="text"]::placeholder {
  color: #777; /* Daha silik placeholder metni */
}

.search-icon {
  background: none;
  border: none;
  cursor: pointer;
  color: #777;
  padding-left: 10px;
}

/* --- ORTA KISIM: LOGO --- */
.header-center {
  flex: 0; /* Otomatik genişlik */
  text-align: center;
  position: absolute; /* Ortalamak için mutlak konumlandırma */
  left: 50%;
  transform: translateX(-50%);
}

.logo {
  width: 129px;
  height:100%;
}


/* --- SAĞ KISIM: İKONLAR --- */
.header-right {
  flex: 1;
  display: flex;
  justify-content: flex-end; /* Sağ tarafa hizala */
  align-items: center;
}

.icon-link {
  color: #333; /* İkon rengi */
  margin-left: 20px;
  position: relative;
  text-decoration: none;
  display: flex;
  align-items: center;
}

.icon-link:hover {
  color: #1a2c5b; /* Hover efekti */
}

.cart-count {
  position: absolute;
  top: -8px;
  right: -10px;
  background-color: black; /* Siyah arkaplan */
  color: white;
  border-radius: 50%;
  padding: 2px 6px;
  font-size: 10px;
  font-weight: bold;
}
</style>