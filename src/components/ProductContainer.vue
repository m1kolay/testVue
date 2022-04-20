<template>
    <div class="productContainer">
        <div class="productContainer__wrapper">
            <ProductFilterPanel :priceSortHandler="priceSortHandler" :nameFilterHandler="nameFilterHandler" :isSorted="isSorted"/>
            <div class="productContainer__products">
                <ProductItem v-for="productItem in filteredItems" :key="productItem.id" :productItem="productItem"/>
            </div>
        </div>
    </div>
</template>

<script>

import ProductFilterPanel from "./common/ProductFilterPanel"
import ProductItem from "./common/ProductItem"
import { ProductItems } from "../constants/mockProductItems"

export default {
    data() {
        return{
            isSorted: false,
            productItems: ProductItems,
            filteredItems: [],
        }
    },
  name: 'ProductContainer',
  components: {
    ProductFilterPanel,
    ProductItem
  },
  methods: {
    priceSortHandler() {
        if(!this.isSorted) {
            this.filteredItems.sort((item1, item2) => item1.price - item2.price)
            this.isSorted = true
        } else {
            this.filteredItems.sort((item1, item2) => item2.price - item1.price)
            this.isSorted = false
        }           
      },
    nameFilterHandler(event){
        const searchValue = event.target.value
        const tempFilterItems = this.productItems.filter(item => item.name.toLowerCase().includes(searchValue.toLowerCase()));
        this.filteredItems = [...tempFilterItems]
    }, 
  },
    watch: {
    question: {
      handler(newQuestion) {
          this.filteredItems = this.productItems
      },
      immediate: true
    }
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
        overflow: hidden;

        &__wrapper {
            padding: 30px;
            height: 100%;

            @media (max-width: 905px) {
                padding: 15px;
            }
        }

        &__products {
            display: grid;
            grid-auto-rows: 168px;
            grid-template-columns: repeat(auto-fill,minmax(168px,1fr));
            grid-gap: 16px;
            grid-auto-flow: row;
            padding-right: 12px;
            max-height: 700px;
            padding-right: 15px;

            @media (max-width:1600px) {
                max-height: 630px;
            }

            @media (max-width:951px) {
                justify-content: center;
                column-gap: 20px;
            }

            @media (max-width:905px) {
                max-height: 515px;
            }

            overflow-y: scroll;
            &::-webkit-scrollbar {
                width: 10px;
            }

            &::-webkit-scrollbar-track {
                background: white;
                box-shadow: 0px 0px 14px rgba(0, 0, 0, 0.02);
                border-radius: 2px;
            }

            &::-webkit-scrollbar-thumb {
                background: #FF9900;
            }

            &:hover {
                &::-webkit-scrollbar-thumb {
                background: #a36302;
            }
            }
        }
    }
</style>