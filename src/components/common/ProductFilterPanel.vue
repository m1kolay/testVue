<template>
    <div class="productFilterPanel">
        <div class="productFilterPanel__filters">
            <input class="productFilterPanel__search" type="text" placeholder="Поиск..." v-on:change="nameFilterHandler($event)"/>
            <div class="productFilterPanel__filter">
                <div class="productFilterPanel__priceFilter" v-on:click="priceSortHandler">
                    <img v-bind:class="{ isSorted: isSorted }" src="../../assets/ProductFilter.svg" alt="filter"/>
                </div>
                <div class="productFilterPanel__popular">
                    <img src="../../assets/star.svg" alt="star"/>
                    <h4>Популярнее</h4>
                </div>
            </div>
        </div>
        <div class="productFilterPanel__buy">
            <div class="productFilterPanel__autoBuy">
                <h4>АВТОПОКУПКИ</h4>
                <img src="../../assets/autoBuy.svg"/>
            </div>
            <div class="productFilterPanel__basket">
                <img src="../../assets/₽.png" alr="rub"/>
                <span>25 285.65</span>
                <div class="productFilterPanel__basketImg">
                    <img src="../../assets/shop.svg" alt="basket"/>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    props: {
            priceSortHandler: Function,
            nameFilterHandler: Function,
            isSorted: Boolean,
        }
}

</script>

<style lang="scss">
    .productFilterPanel {
        display: flex;
        justify-content: space-between;
        padding-bottom: 20px;

        @media (max-width: 1600px) {
            flex-direction: column;
            row-gap: 15px;
            align-items: center;
        }
        
        &__filters {
            display: flex;

            @media (max-width:1080px) {
                width: 100%;
            }

            @media (max-width:905px) {
                flex-direction: column;
                row-gap: 15px;
            }
        }

        &__search {
            background-image: url("../../assets/lupa.svg");
            background-repeat: no-repeat;
            outline: none;
            padding: 19px 19px 19px 85px;
            border-radius: 7px;
            border: none;
            font-size: 20px;
            line-height: 24px;
            background-position: 10%;
            width: 430px;

            &::placeholder {
                color: #D8D8D8;
            }

            @media (max-width:1080px) {
                width: 100%;
            }
        }

        &__filter {
            display: flex;
            align-items: center;
            margin-left: 15px;
            
            img {
                transition: all 0.3s;
            }

            @media (max-width:905px) {
                margin: 0;
            }
        }

        &__priceFilter {
            width:62px;
            height: 62px;
            background: #FF9900;
            border-radius: 7px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;

            .isSorted {
                transform: rotate3d(1, 0, 0, 180deg);
            }

            @media (max-width:905px) {
                width: 100%;
            }
        }

        &__popular {
            cursor: pointer;
            display: flex;
            background: white;
            max-height: 48px;
            align-items: center;
            height: 100%;
            border-radius: 0px 7px 7px 0px;
            padding: 12px 16px;

            img {
                padding-right: 10px;
            }

            h4 {
                font-size: 20px;
                line-height: 24px;
                font-weight: 500;
            }

            @media (max-width:905px) {
                width: 100%;
                justify-content: center;
            }
        }

        &__buy {
            display: flex;

            @media (max-width:1080px) {
                width: 100%;
            }

            @media (max-width:905px) {
                flex-direction: column;
                row-gap: 15px;
            }
        }

        &__autoBuy {
            cursor: pointer;
            display: flex;
            background: #E86F00;
            border-radius: 7px;
            align-items: center;
            justify-content: center;
            padding: 21px;

            h4 {
                font-weight: 600;
                font-size: 20px;
                line-height: 18px;
                color: white;
            }

            img {
                padding-left: 12px;
            }

            @media (max-width:1080px) {
                width: 100%;
            }
        }

        &__basket {
            cursor: pointer;
            box-shadow: 0px 0px 14px rgba(0, 0, 0, 0.02);
            border-radius: 7px;
            background: white;
            padding: 7px 7px 7px 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-left: 30px;
            white-space: nowrap;

            span {
                font-size: 20px;
                line-height: 23px;
                padding-left: 10px;
            }

            @media (max-width:1080px) {
                width: 100%;
            }

            @media (max-width:905px) {
                margin: 0;
            }
        }

        &__basketImg {
            width: 48px;
            height: 48px;
            background: #FF9900;
            box-shadow: 0px 0px 7px rgba(255, 153, 0, 0.47);
            border-radius: 5px;
            margin-left: 20px;
            display: flex;
            justify-content: center;
            align-items: center;

            img {
                width: 23px;
                height: 23px;
            }
        }
    }
</style>