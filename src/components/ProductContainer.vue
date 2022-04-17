<template>
    <div class="productContainer">
        <div class="productContainer__wrapper">
            <ProductFilterPanel/>
            <div class="productContainer__products">
                <ProductItem v-for="productItem in productItems" :key="productItem.id" :productItem="productItem"/>
            </div>
        </div>
    </div>
</template>

<script>

import ProductFilterPanel from "./ProductFilterPanel"
import ProductItem from "./ProductItem"


export default {
    data() {
        return{
        }
    },
  name: 'ProductContainer',
  computed: {
      productItems () {
          return this.$store.state.productItems
      }
  },
  components: {
    ProductFilterPanel,
    ProductItem
  }
}

</script>

<style scoped lang="scss">
    .productContainer {
        width: calc(100% - 360px);
        height: calc(100vh - 100px);
        position: relative;
        left: 360px;
        background: #F6F6F6;

        &__wrapper {
            padding: 30px;
            height: 100%;
        }

        &__products {
            display: flex;
            flex-wrap: wrap;
            row-gap: 20px;
            column-gap: 20px;
        }
    }
</style>