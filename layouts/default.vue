<template>
  <div>
    <!-- Sabit Header (Global Header) -->
    <Header />

    <!-- Sol Menü Sidebar -->
    <Menu />

    <!-- Ana İçerik Alanı -->
    <div class="main-content">
      <!-- Tab Menüsü -->
      <Navbar />

      <!-- Dinamik İçerik -->
      <nuxt />
    </div>
  </div>
</template>

<script>
import Header from '~/components/Header.vue'; // Header bileşenini import ediyoruz
import Menu from '@/components/Menu.vue'; // Sidebar bileşenini import ediyoruz
import Navbar from '@/components/Navbar.vue'; // Yeni Navbar bileşenini import ediyoruz

export default {
  components: {
    Header,
    Menu,
    Navbar, // Navbar'ı ekledik
  },
};
</script>

<style scoped>
/* Genel Sayfa Yapısı */
.page-container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

/* Header'ın Sticky olması için */
header {
  position: sticky;
  top: 0; /* Ekranın üst kısmına sabitlenir */
  z-index: 1000; /* Header'ı diğer içeriklerin üstünde tutar */
  background-color: white;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
}

/* Main Content alanının, sidebar ile uyumlu olması için */
.main-content {
  margin-left: 250px; /* Sidebar genişliği kadar boşluk bırak */
  padding: 20px;
  background-color: #f5f5f5;
  min-height: calc(100vh - 60px); /* Header'ın yüksekliğini çıkar */
}

/* Navbar için ek stil */
.tab-menu {
  margin-left: 250px; /* Sidebar boşluğu ile uyumlu */
  padding: 10px 20px;
  background-color: white;
  border-bottom: 2px solid #e0e0e0;
  position: sticky;
  top: 60px; /* Header'ın altında yapışkan hale getir */
  z-index: 999;
}

.tab-menu ul {
  list-style: none;
  display: flex;
  gap: 20px;
  padding: 0;
  margin: 0;
}

.tab-menu ul li a {
  text-decoration: none;
  color: black;
  padding: 10px 15px;
  font-size: 16px;
  font-weight: bold;
  transition: color 0.3s, border-bottom 0.3s;
}

.tab-menu ul li a.active {
  color: pink;
  border-bottom: 2px solid pink;
}
</style>
