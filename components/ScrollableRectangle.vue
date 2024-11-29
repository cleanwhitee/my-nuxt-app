<template>
  <div class="scrollable-rectangle">
    <div class="scrollable-container">
      <div class="scrollable-item" v-for="(item, index) in items" :key="index">
        <img :src="item.imgSrc" :alt="item.alt" class="item-image" />
        <p class="item-text">{{ item.text }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ScrollableRectangle",
  props: {
    items: {
      type: Array,
      required: true, // Dışarıdan gönderilen items zorunlu
    },
  },
};
</script>

<style scoped>
/* Ana scrollable alanın dış kaplaması */
.scrollable-rectangle {
  width: 100%; /* Alanın sayfanın tamamını kaplaması */
  overflow-x: auto; /* Yatayda kaydırma */
  white-space: nowrap; /* Öğelerin satır içinde tutulması */
  padding: 10px 0;
  background-color: #f9f9f9;
  border: 1px solid #ddd;
  border-radius: 5px;
}

/* Öğelerin gruplandığı konteyner */
.scrollable-container {
  display: flex;
  gap: 15px; /* Öğeler arasındaki mesafe */
}

/* Her bir öğenin görünümü */
.scrollable-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-width: 150px; /* Her öğe için minimum genişlik */
  max-width: 200px; /* Öğe genişliğini sınırlamak için */
  padding: 10px;
  background-color: white;
  border: 1px solid #ccc;
  border-radius: 5px;
  text-align: center;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  flex-shrink: 0; /* Daralma olmaması için */
}

/* Resimlerin stilleri */
.item-image {
  width: 100%; /* Resmin genişliği kapsayıcıya uyacak */
  height: auto; /* Yükseklik oranını korur */
  object-fit: cover; /* Resmi taşıyıcı alana sığdırır */
  border-radius: 5px;
  margin-bottom: 10px;
}

/* Yazı stil ayarları */
.item-text {
  font-size: 14px;
  color: #333;
  margin: 0;
}
</style>
