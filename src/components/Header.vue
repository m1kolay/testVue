<template>
    <header class="header">
        <a href="#" class="header__nav header__nav--opened"><img src="../assets/shop.svg" alt="shop"/>МАГАЗИН</a>
        <a href="#" class="header__nav"><img src="../assets/trade.svg" alt="trade"/>ОБМЕН</a>
        <a href="#" class="header__nav">ИНВЕНТАРЬ</a>
        <a href="#" class="header__nav">F.A.Q</a>
        <div class="header__selectGame">
            <div class="header__selectGameItem header__selectGameItem--selected">
                <img src="../assets/selectGameGun.png" alt="Gun"/>
                <span>MM2</span>
            </div>
            <div class="header__selectGameItem">
                <img src="../assets/selectGameCat.png" alt="Cat"/>
                <span>Adopt Me</span>
            </div>
        </div>
        <div class="header__notification">
            <img src="../assets/notification.svg" alt="notification"/>
        </div>
        <div class="header__select">
            <img src="../assets/ruFlag.png" alt="flag"/>
            <span>RU</span>
            <img class="select__arrow" src="../assets/arrowDown.svg">
        </div>
        <div class="header__select select">
            <img src="../assets/₽.png" alt="flag"/>
            <img class="select__arrow" src="../assets/arrowDown.svg">
        </div>
        <button class="header__login"><img src="../assets/login.svg"/>ЛИЧНЫЙ КАБИНЕТ</button>
    </header>
</template>

<script>

export default {
  name: 'Header',
  components: {
  }
}

</script>

<style lang="scss">
    .header {
        position: relative;
        width: calc(100% - 360px);
        left: 360px;
        max-height: 100px;
        padding: 14px 0px;
        display: flex;
        align-items: center;
        justify-content: space-evenly;

        &__nav {
            padding: 9px 15px;
            font-size: 20px;
            line-height: 23px;
            text-decoration: none;
            color: black;
            display: flex;
            align-items: center;
            white-space: nowrap;

            img {
                padding-right: 12px;
            }
        }

        &__nav--opened {
            background: #FF9900;
            box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.04);
            border-radius: 6px;
            color:white;
        }

        &__selectGame {
            display: flex;
        }

        &__selectGameItem {
            display: flex;
            flex-direction: column;
            background: #F6F6F6;
            box-shadow: inset 0px 0px 8px rgba(0, 0, 0, 0.04);
            border-radius: 8px;
            cursor: pointer;
            height: 72px;
            width: 105px;
            justify-content: center;
            align-items: center;

            img {
                max-width: 40px;
            }

            span {
                font-size: 16px;
                line-height: 18px;
                padding-top: 4px;
            }

            &--selected {
                background: #FF9900;

                span {
                    color:white
                }
            }
        }

        &__notification {
            width: 40px;
            height: 40px;
            background: #FF9900;
            box-shadow: 0px 3px 15px rgba(0, 0, 0, 0.05);
            border-radius: 4.16667px;
            display: flex;
            justify-content: center;
            align-items: center;
            cursor: pointer;
            margin: 0 20px 0 30px;
        }

        &__select {
            display: flex;
            align-items: center;
            border: 1px solid #EFEFEF;
            box-sizing: border-box;
            border-radius: 5px;
            padding: 10px 14px;
            max-height: 46px;
            height: 100%;
            cursor: pointer;
            margin-right: 25px;

            span {
                font-size: 20px;
                line-height: 23px;
                padding-left: 10px;
            }

            .select {
                &__arrow {
                    padding-left: 15px;
                }
            }
        }

        &__login {
            cursor: pointer;
            display: flex;
            max-height: 70px;
            max-width: 290px;
            width: 100%;
            padding: 22px 32px;
            background: #FF9900;
            border-radius: 8px;
            border: none;
            font-weight: 600;
            font-size: 19px;
            line-height: 26px;
            color: white;
            justify-content: space-between;
        }
    }
</style>