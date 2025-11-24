<template>
  <nav class="dropdown-menu-container">
    <div class="menu-icon">&#9776;</div>
    <ul class="menu-list">
      <li v-for="(item, index) in menuItems" :key="index" 
          class="menu-item"
          :class="{ 'has-submenu': item.submenu }"
          @mouseover="showSubmenu(item.name)"
          @mouseleave="hideSubmenu">
        
        <span class="menu-text">{{ item.name }}</span>

        <ul v-if="item.submenu && activeSubmenu === item.name" class="submenu-list">
          <div class="submenu-arrow"></div>

          <li v-for="(sub, subIndex) in item.submenu" :key="subIndex" 
              :class="{ 'submenu-group-title': sub.isTitle }"
              class="submenu-item">
            <span class="submenu-text">{{ sub.name }}</span>
          </li>
        </ul>
      </li>
    </ul>
    <div class="bottom-bar"></div>
  </nav>
</template>

<script>
export default {
  name: 'DropdownMenuWithSubmenu',
  data() {
    return {
      // Mouse ile üzerine gelindiğinde görünen alt menü adını tutar
      activeSubmenu: null, 
      
      // Menü öğeleri, "Mont & Kaban" için alt menü verisi eklendi
      menuItems: [
        { name: 'Menü'},
        { name: 'Takım Elbise',submenu :[
            {name:'Takım elbise' , isTitle:true},
            {name:'Kruvaze Takım Elbise'},
            {name:'Klasik Takım Elbise'},
            {name:'Yelekli Takım Elbise'},
            {name:'Spor Takım Elbise'},
            {name:' Tecno-line Takım Elbise'},
            {name:'Cizgili Takım Elbise'},
            {name:'Slim Fit Takım Elbise'},
            {name:'Regular Fit Takım Elbise'},
            {name:'6 Drop Takım Elbise'},
            {name:'4 Drop Takım Elbise'},
            {name:'Keten Takım Elbise'},
            {name:'Siyah Takım Elbise'},
            {name:'Lacivert Takım Elbise'},
        ] },
        { name: 'Gömlek' },
        { name: 'Triko' },
        { name: 'Mont & Kaban', submenu: [
            { name: 'Mont', isTitle: true },
            { name: 'Klasik Mont' },
            { name: 'Mevsimlik Mont' },
            { name: 'Şişme Mont' },
            { name: 'Bomber Mont' },
            { name: 'Süet Mont' },
            { name: 'Siyah Mont' },
            { name: 'Kaban', isTitle: true },
            { name: 'Klasik Kaban' },
            { name: 'Şişme Kaban' },
            { name: 'Palto' },
            { name: 'Pardösü & Trençkot', isTitle: true }, // Alt başlık olarak stil verilecek
          ] 
        },
        { name: 'Ceket' },
        { name: 'Yelek' },
        { name: 'Pantolon' },
        { name: 'Sweatshirt' },
        { name: 'Tişört' },
        { name: 'Ayakkabı' },
        { name: 'Aksesuar' },
        { name: 'Smokin & Damatlık' },
        { name: 'Ev & İç Giyim' },
        { name: 'Outlet' },
      ],
    };
  },
  methods: {
    showSubmenu(menuName) {
      // Sadece alt menüsü olan öğeler için açılır menüyü göster
      const item = this.menuItems.find(item => item.name === menuName);
      if (item && item.submenu) {
        this.activeSubmenu = menuName;
      }
    },
    hideSubmenu() {
      // Mouse öğeden ayrıldığında alt menüyü gizle
      this.activeSubmenu = null;
    },
  },
};
</script>

<style scoped>
/* Genel Stiller (Öncekiyle Aynı) */
.dropdown-menu-container {
  display: flex;
  align-items: center;
  font-family: Arial, sans-serif;
  background-color: white;
  position: relative;
  z-index: 10; /* Menünün diğer içeriklerin üstünde kalması için */
}

.menu-icon {
  font-size: 24px;
  padding: 0 15px;
  color: #000080;
  display: flex;
  align-items: center;
  user-select: none;
}

.menu-list {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
}

.menu-item {
  position: relative; /* Alt menü pozisyonu için kritik */
  flex-shrink: 0;
}

.menu-text {
  display: block;
  padding: 15px 12px;
  color: #000080;
  font-size: 14px;
  font-weight: bold;
  white-space: nowrap;
  cursor: pointer; /* Üzerine gelme özelliği için */
}

/* Kırmızı Alt Çizgi 

.bottom-bar {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 3px;
    background-color: #A52A2A;
}
*/

/* --- ALT MENÜ STİLLERİ --- */

.submenu-list {
  position: absolute;
  top: 100%; /* Ana menü öğesinin hemen altına konumlandır */
  left: 0;
  /* Alt menü, ana menü öğesinin genişliğinden başlayacak şekilde ayarlandı */
  min-width: 250px; 
  background-color: #fff;
  border: 1px solid #ddd;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  padding: 10px 0;
  list-style: none;
  z-index: 20; /* Ana menüden daha yüksek */
}

.submenu-arrow {
  position: absolute;
  top: -8px; /* Yukarıdaki menünün hemen altına oturt */
  left: 20px;
  width: 0;
  height: 0;
  border-left: 8px solid transparent;
  border-right: 8px solid transparent;
  border-bottom: 8px solid #fff; /* Beyaz iç üçgen */
  z-index: 21;
}

/* Alt Menü Öğeleri */
.submenu-item {
  padding: 5px 15px;
}

.submenu-text {
  display: block;
  font-size: 14px;
  color: #333;
  padding: 5px 0;
  cursor: pointer;
}

.submenu-text:hover {
  color: #000080;   
}

/* Alt Menüdeki Grup Başlıkları (Mont, Kaban vb.) */
.submenu-group-title .submenu-text {
  font-weight: bold;
  color: #000080; /* Mavi başlık rengi */
  padding-top: 10px;
  cursor: default;
}

.submenu-group-title .submenu-text:hover {
  background-color: transparent; /* Başlıkta hover olmasın */
}
</style>