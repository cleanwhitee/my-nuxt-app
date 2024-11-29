<template>
    <nav>
      <ul>
        <li>
          <nuxt-link to="/en-populer" :class="{ active: $route.path === '/en-populer' }">En Popüler</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/en-yeniler" :class="{ active: $route.path === '/en-yeniler' }">En Yeniler</nuxt-link>
        </li>
        <li>
          <nuxt-link to="/en-cok-satanlar" :class="{ active: $route.path === '/en-cok-satanlar' }">En Çok Satanlar</nuxt-link>
        </li>
      </ul>
    </nav>
    <ScrollableRectangle />
  </template>
  
  <script>

   import ScrollableRectangle from '@/components/ScrollableRectangle.vue';
   
  export default {
    name: "Navbar",
  };
  </script>
  
  <style scoped>
  nav ul {
    list-style: none;
    display: flex;
    gap: 20px;
  }
  nav ul li a {
    text-decoration: none;
    color: black;
  }
  nav ul li a.active {
    color: pink;
    border-bottom: 2px solid pink;
  }
  </style>
  