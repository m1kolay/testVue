<template>
    <div class="sideBarFilterItem">
        <h3 class="sideBarFilterItem__title">{{sideBarFilter.title}}</h3>
        <div class="sideBarFilterItem__select">
            <div class="sideBarFilterItem__info">
                <img src="../assets/SideBarFilterItem.png" alt="sideBarImg"/>
                <h4>Показать все</h4>
            </div>
            <img src="../assets/arrowRight.svg" alt="arrowRight"/>
        </div>
    </div>
</template>

<script>

export default {
  props: ['sideBarFilter']
}
</script>

<style scoped lang="scss">
    .sideBarFilterItem {
        display: flex;
        flex-direction: column;
        width:100%;
        padding-top: 15px;
        
        &__title {
            font-weight: 600;
            font-size: 25;
            line-height: 29px;
            padding-bottom: 14px;
        }

        &__select {
            display: flex;
            justify-content: space-between;
            background: #FFFFFF;
            border-radius: 6px;
            border: 1px solid #E0E0E0;
            padding: 15px 20px 15px 15px;
            cursor: pointer;
        }

        &__info {
            display: flex;

            h4 {
                font-size: 20px;
                line-height: 23px;
                font-weight: 500;
                padding-left: 10px;
            }
        }
    }
</style>