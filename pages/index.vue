<template>
  <div class="page">
    <h1>Hoş Geldiniz!</h1>
    <p>Bu bir örnek sayfadır.</p>
    
    <!-- Sekmeler -->
    <div class="tabs">
      <span
        @click="activeTab = 'populer'"
        :class="{ active: activeTab === 'populer' }"
        class="tab"
      >
        En Popüler
      </span>
      <span
        @click="activeTab = 'yeniler'"
        :class="{ active: activeTab === 'yeniler' }"
        class="tab"
      >
        En Yeniler
      </span>
      <span
        @click="activeTab = 'coksatanlar'"
        :class="{ active: activeTab === 'coksatanlar' }"
        class="tab"
      >
        En Çok Satanlar
      </span>
    </div>

    <!-- İçerikler -->
    <div v-if="activeTab === 'populer'" class="tab-content">
      <h2>En Popüler Ürünler</h2>
      <p>Burada en popüler ürünler listelenecek...</p>
    </div>
    <div v-if="activeTab === 'yeniler'" class="tab-content">
      <h2>En Yeniler</h2>
      <p>Burada yeni gelen ürünler listelenecek...</p>
    </div>
    <div v-if="activeTab === 'coksatanlar'" class="tab-content">
      <h2>En Çok Satanlar</h2>
      <p>Burada en çok satan ürünler listelenecek...</p>
    </div>

    <!-- ScrollableRectangle bileşeni -->
    <ScrollableRectangle :items="rectangleItems" />

    <!-- ProductSlider bileşeni -->
    <ProductSlider :items="sliderItems" />
 
    <!-- Carousel Bileşeni -->
    <Carousel />
    <Chatbox />
    <Footer />
    <Tabs />

  </div>
</template>

<script setup>
import { ref } from 'vue';
import ScrollableRectangle from '~/components/ScrollableRectangle.vue';
import ProductSlider from '~/components/ProductSlider.vue';
import Carousel from '~/components/Carousel.vue';
import Chatbox from '~/components/Chatbox.vue';
import Footer from '~/components/Footer.vue';
import Tabs from '~/components/Tabs.vue';

const rectangleItems = [
  { imgSrc: "/images/maskara.jpg", text: "Maskara" },
  { imgSrc: "/images/fondöten.jpg", text: "Fondöten" },
  { imgSrc: "/images/maskara.jpg", text: "Maskara" },
  { imgSrc: "/images/fondöten.jpg", text: "Fondöten" },
  { imgSrc: "/images/maskara.jpg", text: "Maskara" },
  { imgSrc: "/images/fondöten.jpg", text: "Fondöten" },
  { imgSrc: "/images/maskara.jpg", text: "Maskara" },
  { imgSrc: "/images/fondöten.jpg", text: "Fondöten" }
];

const sliderItems = [
  { imgSrc: "/images/slider1.png" },
  { imgSrc: "/images/slider2.png" },
  { imgSrc: "/images/slider3.png" },
  { imgSrc: "/images/slider4.png" },
  { imgSrc: "/images/slider5.png" }

];

const activeTab = ref('populer');
</script>

<style scoped>
.page {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  padding: 10px;
  text-align: center;
}

h1 {
  font-size: 40px;
  margin-bottom: 20px;
}

.tabs {
  display: flex;
  justify-content: center; /* Sekmeleri yatayda ortalar */
  margin-top: 20px;
}

.tab {
  font-size: 18px;
  padding: 10px 20px;
  cursor: pointer;
  margin-right: 30px;
  transition: all 0.3s ease; /* Geçiş animasyonu */
}

.tab:hover {
  color: #d14b88; /* Sekme üzerine gelindiğinde renk değişimi */
  font-size: 22px; /* Font büyütme */
}

.tab.active {
  font-weight: bold;
  color: #d14b88; /* Aktif sekme için renk */
  border-bottom: 2px solid #d14b88; /* Aktif sekme alt çizgi */
}

.tab-content {
  margin-top: 20px;
}

.tab-content h2 {
  font-size: 40px;
}

</style>
