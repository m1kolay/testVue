<template>
  <div class="home">
    <Header />
    <SideBar />
    <ProductContainer/> 
  </div>
</template>

<script>

import SideBar from '@/components/SideBar.vue'
import Header from '@/components/Header.vue'
import ProductContainer from '@/components/ProductContainer.vue'

export default {
  name: 'HomeView',
  components: {
    SideBar,
    Header,
    ProductContainer
  }
}
</script>

<style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Heebo:wght@500;600;700&display=swap');
  body,
  h1,
  h2,
  h3,
  h4,
  p,
  ul[class],
  ol[class]
  {
    margin: 0;
    font-family: 'Heebo', sans-serif;
  }
  *,
  *::before,
  *::after {
    box-sizing: border-box;
  }
  ul[class],
  ol[class] {
    padding: 0;
  }
  .home {
    position: relative;
  }
</style>