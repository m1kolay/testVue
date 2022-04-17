<template>
    <div class="checkbox" v-bind:class="{ checked: isChecked }">
        <input type="checkbox" v-bind:id="type.id" v-bind:name="type.id">
        <label v-bind:for="type.id" v-on:click="isChecked = !isChecked">{{type.name}}</label>
    </div>
</template>

<script>

export default {
  data() {
    return{
      isChecked:false
    }
  },
  props: ['type']
}
</script>

<style scoped lang="scss">
    .checkbox {
      padding: 14px;
      padding-left: 37px;
      font-size: 20px;
      border: 1px solid #EFEFEF;
      box-sizing: border-box;
      border-radius: 6px;
      position:relative;
      width: 47%;
      input {
        appearance: none;
        position: absolute;
        

        &:checked + label::before {
          background-color: #FF9900;
        }

        &:checked + label::after {
          opacity: 1;
        }
      }

      label {
        cursor: pointer;

        &::before {
          content:"";
          display: block;
          width: 24px;
          height: 24px;
          border: 1px solid #EFEFEF;
          background-color: #ffffff;
          box-shadow: 0px 0px 6.4px rgba(255, 255, 255, 0.25);
          border-radius: 4.8px;
          position: absolute;
          top:16px;
          left: 8px;
          z-index: 1;

          transition: background-color .1s linear;
        }

        &::after {
          content: "";
          width: 14px;
          height: 10px;
          display: block;
          background: url("../assets/check.svg") no-repeat;
          position: absolute;
          top: 23px;
          left: 14px;
          z-index: 2;
          opacity: 0;

          transition: opacity .1s linear;
        }
      }
    }
</style>