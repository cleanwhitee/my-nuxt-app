<template>
  <div>
    <!-- ScrollableRectangle komponentini burada çağırıyoruz -->
    <ScrollableRectangle :items="products" />
  </div>
</template>

<script>
import ScrollableRectangle from "@/components/ScrollableRectangle.vue"; // Komponenti import ediyoruz

export default {
  name: "EnPopuler",
  components: {
    ScrollableRectangle, // Komponenti burada tanımlıyoruz
  },
  data() {
    return {
      products: [
        { imgSrc: "https://via.placeholder.com/150", alt: "Ürün 1", text: "Ürün 1 Açıklaması" },
        { imgSrc: "https://via.placeholder.com/150", alt: "Ürün 2", text: "Ürün 2 Açıklaması" },
        { imgSrc: "https://via.placeholder.com/150", alt: "Ürün 3", text: "Ürün 3 Açıklaması" },
        { imgSrc: "https://via.placeholder.com/150", alt: "Ürün 4", text: "Ürün 4 Açıklaması" },
      ],
    };
  },
};
</script>

<style scoped>
h1 {
  text-align: center;
  margin-bottom: 20px;
}
</style>
