<template>
    <div class="productItem" :style="{'borderBottomColor':productItem.rare}">
        <div class="productItem__imgs">
            <img :src="require(`../../assets/pets/${productItem.imgPet}`)" :alt="productItem.id"/>
            <div class="productItem__statuses">
                <img v-for="status in productItem.statuses" :key="status" :src="require(`../../assets/productStatus/${status}`)" :alt="productItem.id"/>
            </div>
        </div>
        <h5 class="productItem__name">
            {{productItem.name}}
        </h5>
        <p class="productItem__age">
            {{productItem.age}}
        </p>
        <span class="productItem__price">
            {{productItem.price}}₽ 
        </span>
    </div>
</template>

<script>

export default {
  props: [`productItem`]
}
</script>

<style scoped lang="scss">
    .productItem {
        border-bottom: 5px solid;
        display: flex;
        flex-direction: column;
        max-width: 168px;
        width: 100%;
        padding: 17px 16px 11px 16px;
        background: white;
        border-radius: 4px;
        max-height: 170px;
        cursor: pointer;

        @media (max-width: 763px) {
            max-width: none;
            align-items: center;
        }

        &__imgs {
            display: flex;
            justify-content: end;

            @media (max-width: 763px) {
                width: 100%;
                position: relative;
                
                img {
                    &:first-child {
                        margin: 0 auto;
                    }
                }
            }
        }

        &__statuses {
            display: flex;
            flex-direction: column;
            padding-left: 25px;
            justify-content: space-around;

            @media (max-width: 763px) {
                position: absolute;
                height: 70px;
            }
        }

        &__name {
            margin: 10px 0 0;
            font-weight: 600;
            font-size: 15px;
            line-height: 18px;
        }
        
        &__age {
            font-size: 14px;
            color: #717171;
            line-height: 18px;
            padding-top: 4px;
        }

        &__price {
            font-weight: 700;
            font-size: 20px;
            line-height: 18px;
            color: #242424;
            padding-top: 4px;
        }
    }
</style>