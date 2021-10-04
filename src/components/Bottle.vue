<template>
  <div class="bottle" @click="bottleClick()">
      <div class="bottle-inner">
          <span v-for="(color, key) in data" :key="key" :class="color"></span>
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
  created: {

  },
  methods: {
    bottleClick(){
        console.log("click")
    }
  }
}
</script>

<style lang="scss">
.bottle{
   display: block;
   width: 30px;
   height: 100px;
   margin: 20px;
   border-width: 0 2px 2px 2px;
   border-radius: 0 0 15px 15px;
   overflow: hidden;
   border-style: solid;
   border-color: #000;
   cursor: pointer;
   transition: all .15s ease;
   &:hover{
       transform: translateY(-15px);
   }
   &-inner{
        display: flex;
        flex-direction: column;
        height: 100px;
        background: #fff;
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
