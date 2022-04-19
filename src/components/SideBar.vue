<template>
  <div class="sideBar">
    <div class="sideBar__container">
      <img src="../assets/Logo.png" alt="logo"/>
      <div class="sideBar__priceRange">
        <h3>Цена</h3>
        <input placeholder="0.00" :value="lowerRange" :onChange="lowerInputOnChange"/><span>-</span><input :value="upperRange" :onChange="upperInputOnChange" placeholder="∞"/>
        <Slider :modelValue="[lowerRange, upperRange]" :max="1000" :step="10" class="slider-orange" @update="sliderOnUpDate"/>
      </div>
      <h3 class="sideBar__typeTitle">Тип</h3>
      <form class="sideBar__types">
        <CheckboxItem v-for="type in productsTypes" :key="type.id" :type="type"/>
      </form>
      <SideBarFilterItem v-for="sideBarFilter in sideBarFilters" :key="sideBarFilter.id" :sideBarFilter="sideBarFilter"/>
    </div>
    <div class="sideBar__footer footer">
      <div class="footer__head">
        <h4 class="footer__title">Есть вопросы ?</h4>
        <img class="footer__cat" src="../assets/cat.png" alt="cat"/>
        <div class="footer__chat">
          <img src="../assets//chatSvg.svg" alt="chat"/>
        </div>
      </div>
      <div class="footer__socials">
          <a v-for="socialsLink in socialsLinks" :key="socialsLink.id" :href="socialsLink.href" target="blank">
          <img :src="require(`../assets/socials/${socialsLink.src}`)" />
          </a>
      </div>
      <div class="footer__nav">
        <div class="footer__links">
          <a href="#">КОНТАКТЫ</a>
          <a href="#">ПОЛЬЗОВАТЕЛЬСКОЕ СОГЛАШЕНИЕ</a>
          <a href="#">ПОЛИТИКА КОНФИДЕНЦИАЛЬНОСТИ</a>
        </div>
        <p>( C ) COPYRIGHT STARPETS.GG 2020-2022</p>
      </div>
      <p class="footer__info">BENEFICIARY: CRYSTAL FUTURE OU<br/> REG. NUMBER: 14198230<br/> BENEFICIARY’S ADDRESS: HARJU MAAKOND, TALLINN, KESKLINNA LINNAOSA, PIKK TN 7-5</p>
    </div>
  </div>
</template>

<script>

import CheckboxItem from "./common/CheckboxItem.vue"
import SideBarFilterItem from "./common/SideBarFilterItem"
import Slider from '@vueform/slider'

export default {
  data() {
    return{
      lowerRange: 0,
      upperRange:1000,
      productsTypes: [
        {
          name:"Яйцо",
          id:"egg",
        },
        {
          name:"Питомец",
          id:"pet",
        },
        {
          name:"Флай",
          id:"fly",
        },
        {
          name:"Райд",
          id:"ride",
        },
      ],
      sideBarFilters: [
        {
          title:"Редкость",
          id:1,
        },
        {
          title:"Уровень",
          id:2,
        }
      ],
      socialsLinks: [
        {
          src:"tiktok.svg",
          href:"https://www.tiktok.com/",
          id:1,
        },
        {
          src:"instagram.svg",
          href:"https://www.instagram.com/",
          id:2,
        },
        {
          src:"telegram.svg",
          href:"https://web.telegram.org/",
          id:3,
        },
        {
          src:"discord.svg",
          href:"https://discord.com/",
          id:4,
        },
        {
          src:"youtube.svg",
          href:"https://www.youtube.com/",
          id:5,
        },
        {
          src:"twitter.svg",
          href:"https://twitter.com/",
          id:6,
        },
        {
          src:"facebook.svg",
          href:"https://www.facebook.com/",
          id:7,
        },

      ]
    }
  },
  components: {
    CheckboxItem,
    SideBarFilterItem,
    Slider
  },
  methods: {
    sliderOnUpDate(e) {
      [this.lowerRange, this.upperRange] = e
    },
    lowerInputOnChange(e) {
      this.lowerRange = e.target.value
    },
    upperInputOnChange(e) {
      this.upperRange = e.target.value
    }
  }
}
</script>

<style src="@vueform/slider/themes/default.css"></style>
<style scoped lang="scss">
  .sideBar {
    position: fixed;
    max-width: 360px;
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100vh;
    justify-content: space-between;
    width: 100%;
    top: 0;

    &__container {
      padding: 30px 37px 0 33px;
    }

    h3 {
      font-weight: 600;
      font-size: 25px;
      line-height:29px;
      width:100%;
    }

    .slider-orange {
      margin-top: 30px;
      --slider-connect-bg: orange;
      --slider-tooltip-bg: orange;
      --slider-handle-ring-color: orange;
    }

    &__priceRange{
      padding-top: 15px;

      input {
        background-image: url("../assets/₽.png");
        background-repeat: no-repeat;
        border: 1px solid #EFEFEF;
        box-sizing: border-box;
        border-radius: 5px;
        padding:10px 15px 10px 35px;
        outline: none;
        font-size:20px;
        font-weight: 500;
        max-width: 130px;
        background-position: 10% 45%;
        text-align: center;
        font-family: 'Heebo', sans-serif;
        &::placeholder {
          color:#DFDFDF;
        }
        &:last-child {
          &::placeholder {
            font-size: 25px;
          }
        }
      }
    }

    span {
      padding: 0 10px;
      font-weight: 500;
      font-size: 19px;
    }

    &__typeTitle {
      padding: 10px 0;
    }

    &__types {
      display: flex;
      flex-wrap: wrap;
      justify-content: space-between;
      align-content: space-between;
      height: 130px;

      .checked {
        border: 1px solid #FF9900;
        box-shadow: 0px 0px 10px rgba(255, 153, 0, 0.1);
      }
    }

    &__footer {
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 100%;
      max-height: 360px;
      height:100%;
      background-image: url("../assets/footer.png");
      background-repeat: no-repeat;
      background-position: bottom;
      justify-content: end;

      .footer {

        &__head {
          position: relative;
          bottom: 16px;
          right: 15px;
        }

        &__chat {
          width: 82px;
          height: 82px;
          position: absolute;
          display: flex;
          align-items: center;
          justify-content: center;
          background: #FF9900;
          border-radius: 45px;
          bottom:0;
          left: 132px;
          cursor: pointer;
          z-index: 3;
        }

        &__title {
          font-size:16px;
          line-height: 18px;
          font-weight: 500;
          width: 144px;
          height: 41px;
          background: white;
          display: flex;
          align-items: center;
          padding-left: 12px;
          position: relative;
          bottom: 20px;
          left: 0px;
        }

        &__cat {
          position: absolute;
          z-index: 2;
          top:-102px;
          left:125px;
        }

        &__socials {
          display: flex;
          width: 100%;
          align-items: center;
          justify-content: space-around;
          position:relative;
          top:18px;
        }

        &__nav {
          display:flex;
          padding:20px 12px 12px;
          width:100%;
          height: 80px;
          justify-content: space-between;

            p {
              font-size: 10px;
              line-height: 11px;
              text-align: right;
              color:white;
              max-width: 120px;
              display: flex;
              align-items: end;
            }
        }

        &__links {
          display: flex;
          flex-direction: column;
          justify-content: space-between;
          

          a {
            font-size: 10px;
            line-height: 11px;
            font-weight: 500;
            text-decoration: none;
            color:white;
            opacity:0.3;

            &:hover {
              opacity: 1;
            }
          }
        }

        &__info {
          
          padding: 0 6px 9px;
          color:white;
          font-size: 8px;
          line-height: 9px;
        }
      }
    }
  }
</style>
