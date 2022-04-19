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
        <div class="header__burger">
            <span></span>
        </div>
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
        height: 100px;
        padding: 14px 5px 14px 0;
        display: flex;
        align-items: center;
        justify-content: space-evenly;

        @media (max-width:1080px) {
            justify-content: end;
            padding-right: 20px;
        }

        &__nav {
            padding: 9px 15px;
            font-size: 20px;
            line-height: 23px;
            text-decoration: none;
            color: black;
            display: flex;
            align-items: center;
            white-space: nowrap;

            @media (max-width: 1720px) {
                font-size: 17px;
            }

            img {
                padding-right: 12px;
            }

            @media (max-width:1240px) {
                font-size: 14px;
            }

            @media (max-width:1080px) {
                display: none;
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

            @media (max-width:1520px) {
                width: 75px;
                height: 60px;
            }

            @media (max-width:1460px) {
                display: none;
            }

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

            @media (max-width:1700px) {
                margin: 0 5px 0 10px;
            }

            @media (max-width:1460px) {
                display: none;
            }
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

            @media (max-width:1548px) {
                margin-right: 10px;;
            }

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

            @media (max-width: 1250px) {
                padding: 3px 6px;    

                span {
                    display: none;
                }
            }

            @media (max-width:1080px) {
                display: none;
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

            @media (max-width: 1720px) {
                padding: 10px;
                font-size: 15px;
                max-width: 200px;
                align-items: center;
            }

            @media (max-width:1240px) {
                justify-content: center;
                white-space: nowrap;

                img {
                    display: none;
                }
            }

            @media (max-width:1080px) {
                display: none;
            }
        }

        &__burger {
            display: none;
            cursor: pointer;

            @media (max-width:1080px) {
                display: block;
                position: relative;
                width: 30px;
                height: 20px;
            }

            &:before,
            &:after {
                content: "";
                background: black;
                position: absolute;
                width: 100%;
                height: 2px;
                left: 0;
            }

            &:before {
                top:0;
            }

            &::after {
                bottom:0;
            }

            span {
                position: absolute;
                background: black;
                left: 0;
                width: 100%;
                height: 2px;
                top: 9px;
            }
        }
    }
</style>