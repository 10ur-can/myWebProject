<template>
  <footer class="app-footer">
    <div class="footer-content">
      
      <div class="footer-columns">
        
        <div class="footer-col col-corporate">
          <h3>KURUMSAL</h3>
          <ul>
           <li v-for="kurumsalfooter in kurumsal"><a href="#">{{ kurumsalfooter }}</a></li>
          </ul>
          <div class="certificates">
            
            <img v-bind:src="efatura" alt="EBBS Kabulü" class="cert-img">
            <img v-bind:src="klogo" alt="Great Place To Work" class="cert-img">
        
          </div>
        </div>

        <div class="footer-col col-help">
          <h3>YARDIM</h3>
          <ul>
            <li v-for="yardimfoter in yardim"><a href="#">{{ yardimfoter }}</a></li>
          </ul>
        </div>

        <div class="footer-col col-contact">
          <h3>BİZE ULAŞIN</h3>
          <ul>
            <li v-for = "iletisimfooter in iletisim"><a href="#">{{ iletisimfooter }}</a></li>
          </ul>
          
          <h3 class="mt-20">MOBİL UYGULAMAMIZI İNDİRİN</h3>
          <div class="app-links">
            
            <img v-bind:src="appstore" alt="App Store" class="app-icon">
            <img v-bind:src="playstore" alt="Google Play" class="app-icon">
  
          </div>
        </div>
        
        <div class="footer-col col-legal">
          <h3>YASAL UYARILAR</h3>
          <ul>
            <li v-for="yasaluyarilar in yasaluyarilar"><a href=#>{{ yasaluyarilar }}</a></li>
          </ul>

          <h3 class="mt-20">KVKK VE GİZLİLİK</h3>
          <ul>
            <li v-for="gizlilik in gizlilik"><a href="#">{{ gizlilik }}</a></li>
          </ul>
        </div>
         
        <div class="footer-col col-social-newsletter">
          <h3>BİZİ TAKİP EDİN</h3>

          <ul class="social-links">
            <!--
            <li><a href="#"><img src="instagram-icon.png" alt="Instagram" class="icon"> Instagram</a></li>
            <li><a href="#"><img src="facebook-icon.png" alt="Facebook" class="icon"> Facebook</a></li>
            <li><a href="#"><img src="youtube-icon.png" alt="YouTube" class="icon"> YouTube</a></li>
            <li><a href="#"><img src="tiktok-icon.png" alt="TikTok" class="icon"> TikTok</a></li>
            <li><a href="#"><img src="ki-blog-icon.png" alt="Kığılı Blog" class="icon"> Kığılı Blog</a></li>
          -->
          </ul>
          <h3 class="mt-20">E-BÜLTEN</h3>
          <p class="newsletter-text">Kampanyaları Kaçırmayın! E-posta listemize kayıt olun.</p>
          <div class="newsletter-form">
            <input type="email" placeholder="E-posta">
            <button>&gt;</button>
          </div>
          <p class="consent-text">Tarafıma kampanya, tanıtım, reklam içerikli elektronik ticari ileti gönderilmesine izin veriyorum.</p>
          <p class="consent-link">Elektronik Ticari İleti Aydınlatma Metni'mize buradan ulaşabilirsiniz.</p>

          <h3 class="mt-20">KATALOGLARIMIZ</h3>
          <div class="catalog-links">
            <!--
            <img src="katalog-sonbahar.jpg" alt="Sonbahar/Kış Kataloğu" class="catalog-img">
            <img src="katalog-yeni-yil.jpg" alt="Yeni Yıl Hediye Kataloğu" class="catalog-img">
          -->
          </div>
        </div>
      </div>
      
      <div class="footer-bottom">
        <p class="copyright">© 2025 Kığılı, Türkiye'nin Erkek Giyim Markası, Holly Palm Tarafından Desteklenir.</p>
        <div class="payment-methods">
            <!--
          <img src="visa-icon.png" alt="Visa" class="payment-icon">
          <img src="mastercard-icon.png" alt="Mastercard" class="payment-icon">
          <img src="troy-icon.png" alt="Troy" class="payment-icon">
        -->
        </div>
      </div>
      
      <div class="live-chat-button">
       <!-- <img src="live-chat-icon.png" alt="Canlı Destek"> -->
      </div>
    </div>
  </footer>
</template>

<script>
import efatura from '@/assets/images/efatura.png'
import klogo from '@/assets/images/klogo.png'
import appstore from '@/assets/images/appstore.png'
import playstore from '@/assets/images/playstore.png'

export default {
  name: 'AppFooter',
  // Bu bileşen statik içerik içerdiği için şimdilik data veya methods gerekmemektedir.
  // Ancak e-bülten kaydı gibi dinamik bir alan eklenirse burası kullanılabilir.
  data(){
    return{
     kurumsal :[
    'Hakımızda',
    'Franchazing',
     'Kurunsal satıs',
     'Insan Kayankları',
     'Cayiz & Home Bayilik',
     'Site Haritası'
    ],
    yardim :[
      'Kampanya Bilgilendirme',
      'Ödeme Secenenekleri',
      'Teslimat',
      'iade ve Degisim',
      'Kolay İade Bilgilendirme',
      'Sıkca Sorulan Sorular',
      'Takım Elbise Kalıpları',
      'Ceket Kalıpları',
      'Bedenimi Bul',
      'Sipariş Sorgulama'
    ],
    iletisim :[
      'İletisim',
      'Magazalarımız',
      'Kigili Destek',
      'Whatsapp Asistan'
    ],
    yasaluyarilar :[
      'Kullanım Kosulları',
      'Güvenlik Bildirgesi',
      'Bilgi Toplum Hizmetleri',
    ],
    
    gizlilik :[
   'İnternet Sitesi Ziyaretçi ve Müşteri Aydınlatma Metni',
    'Çalışan ve Stajyer Adayı Aydınlatma Metni',
    'Elektronik Ticari İleti Metni',
    'Tedarik Yetkili/Çalışanı Metni',
    'Elektronik Ticari İleti İzni',
    'Çerez Politikası',
    ],

    efatura : efatura,
    klogo : klogo,
    appstore : appstore,
    playstore : playstore
    }
  }
}
</script>

<style scoped>
/* ---------------------------------- */
/* Genel Stil ve Responsive Yaklaşım */
/* ---------------------------------- */
.app-footer {
  background-color: #f8f8f8; /* Arka plan rengi */
  padding: 40px 20px 20px;
  color: #555;
  font-family: sans-serif;
}

.footer-content {
  max-width: 1200px; /* İçeriği merkezleme */
  margin: 0 auto;
  position: relative;
}

/* Sütunlar (Responsive Flexbox) */
.footer-columns {
  display: flex;
  flex-wrap: wrap; /* Gerekirse alt satıra geç */
  justify-content: space-between;
  margin-bottom: 30px;
}

.footer-col {
  /* Büyük ekranlarda 5 sütun (her biri yaklaşık %20 genişlikten biraz az) */
  flex: 1 1 20%; 
  min-width: 200px; /* Minimum sütun genişliği, mobil uyumu için önemli */
  padding: 10px 15px;
  box-sizing: border-box;
}

/* Mobil Uyum (768px altı) */
@media (max-width: 768px) {
  .footer-col {
    /* Mobil cihazlarda her sütun %50 genişliğinde */
    flex: 1 1 50%;
    margin-bottom: 20px;
  }
  /* Çoklu içerik sütunu (Sosyal + Bülten) mobil 50% genişlikten devam eder */
  .col-social-newsletter {
    flex: 1 1 100%; /* Tüm genişliği kapla */
  }
}

/* ---------------------------------- */
/* Tipografi ve Liste Stilleri */
/* ---------------------------------- */

.footer-col h3 {
  font-size: 14px;
  color: #333;
  margin-top: 0;
  margin-bottom: 15px;
  font-weight: bold;
}

.footer-col ul {
  list-style: none;
  padding: 0;
  margin: 0;
}

.footer-col li {
  margin-bottom: 8px;
}

.footer-col a {
  text-decoration: none;
  color: #555;
  font-size: 13px;
}

.footer-col a:hover {
  color: #000;
}

.icon {
  width: 16px;
  height: 16px;
  vertical-align: middle;
  margin-right: 5px;
}

.mt-20 {
  margin-top: 20px;
}

/* ---------------------------------- */
/* Özel Alanlar Stilleri */
/* ---------------------------------- */

/* Sertifikalar */
.certificates {
  margin-top: 20px;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.cert-img {
  max-width: 100px;
  height: auto;
}

/* Uygulama Bağlantıları */
.app-links {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.app-icon {
  max-width: 130px;
  height: auto;
}

/* E-Bülten Formu */
.newsletter-form {
  display: flex;
  margin: 10px 0;
  border: 1px solid #ccc;
}

.newsletter-form input {
  padding: 10px;
  border: none;
  flex-grow: 1;
  font-size: 13px;
}

.newsletter-form button {
  background-color: #555;
  color: white;
  border: none;
  padding: 10px 15px;
  cursor: pointer;
  font-weight: bold;
}

.newsletter-text, .consent-text, .consent-link {
    font-size: 12px;
    margin-bottom: 5px;
}

/* Katalog Görselleri */
.catalog-links {
  display: flex;
  gap: 10px;
  margin-top: 15px;
}

.catalog-img {
  width: 100px; /* Görseldeki boyuta yakın bir genişlik */
  height: auto;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

/* ---------------------------------- */
/* Alt Footer ve Ödeme Yöntemleri */
/* ---------------------------------- */

.footer-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-top: 1px solid #ddd;
  padding-top: 20px;
}

.copyright {
  font-size: 12px;
  color: #777;
}

.payment-methods {
    display: flex;
    gap: 10px;
}

.payment-icon {
    height: 18px; 
    width: auto;
}

/* Yeşil Canlı Destek Butonu (Footer'ın dışında, sabit) */
.live-chat-button {
    position: fixed;
    bottom: 20px;
    right: 20px;
    width: 40px;
    height: 40px;
    background-color: #4CAF50;
    border-radius: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    cursor: pointer;
    z-index: 1000;
}

.live-chat-button img {
    width: 20px;
    height: 20px;
    filter: invert(1); /* Beyaz ikon için */
}

/* Mobil Alt Footer */
@media (max-width: 600px) {
  .footer-bottom {
    flex-direction: column;
    align-items: center;
    text-align: center;
  }
  .copyright {
    margin-bottom: 10px;
  }
}
</style>