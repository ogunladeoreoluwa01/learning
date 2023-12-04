<template>
<h1>Reaction timer</h1>
<button @click="startGame()" :disabled="showblock"> start</button>
<ResultComp v-if="showreult" :score="score"/>
<block v-if="showblock" :delay="delay" @end="endgame"/>



</template>



<script>

import block from './components/block-comp.vue'
import ResultComp from './components/result-comp.vue'


export default {

  data(){
    return{
      delay:null,
showblock:false,
showreult:false,
score:null
    }
  },
  name: 'App',
  components: {
    block,
    ResultComp
},
  methods: {
    startGame(){
this.delay=2000+Math.random()*5000
      this.showblock=!this.showblock
      console.log(this.delay)
      this.showreult=false
    },
    endgame(reaction){
this.score=reaction
this.showblock=!this.showblock
this.showreult=true
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  display: flex;
  gap: 20px;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
button{
  padding: 10px;
  width: 60px;
 
  
}
</style>
