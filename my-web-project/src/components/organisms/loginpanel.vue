<template>
  <div class="menu-container">
    <div class="login-button">
      Giriş Yap
    </div>

    <ul class="menu-list">
      <li class="menu-item">
        <i class="icon-person"></i>
        Kayıt Ol
      </li>

      <li class="menu-item">
        <i class="icon-package"></i>
        Sipariş Takip
      </li>

      <li class="divider"></li>

      <li class="menu-item support-item">
        Kiğılı Destek
        <i class="icon-arrow-right"></i>
      </li>
      <li class="menu-item">
        Mağazalarımız
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'MenuComponent'
}
</script>

<style scoped>
/* Genel Konteyner Stilleri (İstenen Boyutlar) */
.menu-container {
  width: 240px;
  height: 225px;
  padding: 10px;
  box-sizing: border-box; /* Padding'i boyut içine dahil eder */
  background-color: #ffffff;
}

/* Giriş Yap Butonu Stilleri */
.login-button {
  background-color: #333333;
  color: white;
  text-align: center;
  padding: 12px 0;
  margin-bottom: 10px;
  font-weight: bold;
  font-size: 16px;
  cursor: pointer;
  transition:0.5s;
}

.login-button:hover{
    background-color: #070707; 
}

/* Liste Stilleri */
.menu-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.menu-item {
  display: flex;
  align-items: center;
  padding: 8px 0;
  font-size: 15px;
  color: #333333;
  cursor: pointer;
}

.menu-item:hover {
  background-color: #f5f5f5; /* Hover efekti ekleyebiliriz */
}

/* Ayırıcı Çizgi */
.divider {
  border-top: 1px solid #e0e0e0;
  margin: 10px 0;
}

/* Destek Öğesi için Ek Stiller (Ok işaretini sağa yaslamak için) */
.support-item {
  justify-content: space-between;
}

/* İkonlar için yer tutucular (Gerçek projede font ikon kütüphanesi kullanılmalıdır) */
.icon-person::before {
  content: ''; 
  margin-right: 10px;
}
.icon-package::before {
  content: '';
  margin-right: 10px;
}
.icon-arrow-right::before {
  content: '→';
  margin-left: 10px;
  font-weight: bold;
  position:relative;
  left:-110px;
  
}
</style>