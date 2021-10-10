<template>
  <div class="bottle" @click="bottleClick()" :class="data.checked === true ? 'active' : '' ">
      <div class="bottle-inner">
          <span v-for="(color, key) in data.colors" :key="key" :class="color"></span>
      </div>
  </div>
</template>

<script>
export default {
  name: 'Bottle',
  props: ['data'],
  data() {
    return {
      msg: "message"
    }
  },
  computed:{

  },
  methods: {
    bottleClick(){
       this.$emit("bottleClick", this.data);
    }
  }
}
</script>

<style lang="scss">
.bottle{
   display: block;
   position: relative;
   width: 40px;
   height: 135px;
   margin: 20px;
   border-width: 2px 2px 2px 2px;
   border-radius: 0 0 20px 20px;
   overflow: hidden;
   border-style: solid;
   border-color: #000;
   cursor: pointer;
   transition: all .15s ease;
   &:hover, &.active{
       transform: translateY(-15px);
   }
   &-inner{
        display: flex;
        flex-direction: column;
        height: 120px;
        background: #fff;
        position: absolute;
        left: 0;
        bottom: 0px;
        width: 100%;
        span{
            display: block;
            height: 100%;
            width: 100%;
            &.blue{
                background: blue;
            }
            &.red{
                background: red;
            }
            &.yellow{
                background: yellow;
            }
            &.green{
                background: green;
            }
        }
   }
   
}
</style>
