<template>
  <div>
    <div class="game-wrap">
      <bottle v-for="(bottle, key) in bottles" :key="key" :data="bottle" v-on:bottleClick="bottleClick"/>
    </div>
  </div>
</template>

<script>
import Bottle from './Bottle.vue'

export default {
  components: { Bottle },
  name: 'GameScreen',
  data() {
    return {
      level: 1,
      bottlesCount: 3,
      bottleSize: 4,
      bottles: [],
      colors: ['red', 'blue', 'green', 'yellow'],
      emptyBottle: [false, false, false ,false]
    }
  },
  computed:{

  },
  created() {
    let i = 0;
    while (i < this.bottlesCount) {
      this.bottles.push(this.createBottle())
      i++
    }
    this.bottles.push(this.emptyBottle)

  },
  methods: {
    createBottle(){
        let i = 0
        const bottle = {}
        bottle.colors = [];
        while(i < this.bottleSize){
          i++
          bottle.colors.push(this.colors[Math.floor(Math.random() * this.colors.length)])
        }
        bottle.checked = false
      return bottle
    },
    bottleClick(data){
      this.resetAllBottles();
      data.checked = true
    },
    resetAllBottles(){
      this.bottles.forEach(element => {
        element.checked = false
      });
    }
  }
}
</script>

<style scoped lang="scss">
.game-wrap{
  display: flex;
  height: 100vh;
  width: 100%;
  align-items: center;
  justify-content: center;
}
</style>
