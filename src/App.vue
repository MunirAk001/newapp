
<template>
  <h1> Code 1999: .. Reaction Timer </h1>
<button @click="start" :disabled="isplaying">Play</button>

<Black v-if="isplaying" :delay ="delay" @end="endgame" />
<Result v-if="showresult" :scoer="scoer"/>
</template>


  <script >
  import Black from './components/Block.vue'
import Result from './components/Result.vue'
  export default {
    name: 'App',
    components: {Black, Result},
data(){
  return{
    delay: null,
    isplaying: false,
    showresult: false,
    scoer: null
  }
},
    
    methods:{
    start(){
      this.delay = 1000 + Math.random() * 5000
      this.isplaying = true
this.showresult = false

    },
    endgame(timer){
this.scoer = timer
this.isplaying = false
this.showresult = true
    }
    }
  }
  </script>

<style >
#app{
  color: rgba(1, 1, 1, 0.5);
  font: 1em sans-serif;
}
button{
  background: rgb(108, 3, 228);

  color: rgb(255, 255, 255);
  border: none;
  padding: 8px 16px;
  border-radius: 5px;
  font-size: 16px;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
  width: 250px;
}
</style>
