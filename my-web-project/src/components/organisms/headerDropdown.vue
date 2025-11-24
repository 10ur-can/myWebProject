<template>
  <nav class="main-nav">
    <ul class="nav-list">
      <li 
        v-for="(item, index) in menuData" 
        :key="index" 
        class="nav-item"
        @mouseenter="setActiveMenu(item.title)"
        @mouseleave="setActiveMenu(null)"
      >
        <a :href="item.link">{{ item.title }}</a>

        <div 
          v-if="item.subcategories && activeMenu === item.title" 
          class="dropdown-content"
        >
          <div class="dropdown-container">
            <div class="dropdown-column" v-for="(col, colIndex) in item.subcategories" :key="colIndex">
              
              <h3 v-if="col.title">{{ col.title }}</h3>
              
              <ul>
                <li v-for="(subItem, subIndex) in col.items" :key="subIndex">
                  <a :href="subItem.link">{{ subItem.name }}</a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'MainMenu',
  data() {
    return {
      // Fare imlecinin üzerinde bulunduğu aktif menünün başlığı
      activeMenu: null, 
      
      // Yüklediğiniz görsellerdeki menü başlıklarını ve alt yapılarını içeren veri
      menuData: [
        { title: 'Menü', link: '#' },
        { title: 'Takım Elbise', link: '#' },
        { title: 'Gömlek', link: '#' },
        { title: 'Triko', link: '#' },
        { 
          title: 'Mont & Kaban', 
          link: '#', 
          // Örnek multi-kolon yapısı
          subcategories: [
            { 
              title: 'Mont', 
              items: [
                { name: 'Klasik Mont', link: '#' },
                { name: 'Mevsimlik Mont', link: '#' },
                { name: 'Şişme Mont', link: '#' },
                { name: 'Bomber Mont', link: '#' },
              ]
            },
            { 
              title: 'Kaban', 
              items: [
                { name: 'Klasik Kaban', link: '#' },
                { name: 'Şişme Kaban', link: '#' },
                { name: 'Palto', link: '#' },
              ]
            },
            { 
              title: 'Pardösü', 
              items: [
                { name: 'Trençkot', link: '#' },
                { name: 'Yağmurluk', link: '#' },
              ]
            }
          ] 
        },
        { title: 'Ceket', link: '#' },
        { title: 'Yelek', link: '#' },
        { title: 'Pantolon', link: '#' },
        { title: 'Sweatshirt', link: '#' },
        { title: 'Tişört', link: '#' },
        { title: 'Ayakkabı', link: '#' },
        { title: 'Aksesuar', link: '#' },
        { title: 'Smokin & Damatlık', link: '#' },
        { title: 'Ev & İç Giyim', link: '#' },
        { title: 'Outlet', link: '#' },
      ]
    };
  },
  methods: {
    /**
     * Fare imlecinin üzerine gelinen menü başlığını ayarlar.
     * @param {string | null} menuTitle - Üzerine gelinen menünün başlığı (ya da null)
     */
    setActiveMenu(menuTitle) {
      this.activeMenu = menuTitle;
    }
  }
};
</script>

<style scoped>
/* ---------------------------------- */
/* CSS Stilleri (Görünüm) */
/* ---------------------------------- */

.main-nav {
  position: relative; 
  background-color: white;
  /* Kırmızı çizgi */
  border-bottom: 3px solid #b71c1c; 
}

.nav-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: flex-start; 
}

/* Her Bir Üst Menü Ögesi */
.nav-item {
  position: relative; 
  padding: 12px 15px;
  cursor: pointer;
  z-index: 10;
}

.nav-item a {
  text-decoration: none;
  /* Görseldeki lacivert metin rengi */
  color: #1a237e; 
  font-weight: bold;
  font-size: 14px;
}

.nav-item:hover a {
    color: #b71c1c; /* Hover rengini kırmızı yap */
}

/* Dropdown İçeriği (Geniş Açılır Alan - drowdown3.png) */
.dropdown-content {
  position: absolute;
  left: 0; 
  right: 0;
  top: 100%; 
  background-color: white;
  box-shadow: 0 4px 8px rgba(0,0,0,0.15);
  padding: 20px 40px;
  z-index: 50; 
  text-align: left;
  /* Ana menü çubuğunun genişliğine göre ayarlanır */
  width: 100vw; 
  transform: translateX(-50%); /* Ortalamak için */
  left: 50%;
}

.dropdown-container {
  display: flex; 
  justify-content: flex-start;
  max-width: 1200px; /* İçeriği merkezle */
  margin: 0 auto;
}

.dropdown-column {
  flex: 1; 
  min-width: 180px;
  padding-right: 30px;
}

.dropdown-column h3 {
  font-size: 14px;
  color: #1a237e; 
  margin-top: 0;
  margin-bottom: 12px;
  font-weight: bold;
}

.dropdown-column ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.dropdown-column ul li {
  padding: 4px 0;
}

.dropdown-column ul li a {
  font-weight: normal;
  color: #555;
  font-size: 13px;
}
</style>