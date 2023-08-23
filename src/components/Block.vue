<template>
  <div class="black" v-if="showBlack" @click=" stopTimer">Click me</div>
</template>

<script>  

export default {
props:['delay'],
data(){
  return{
    showBlack: false,
    timer:null,
    reactionTimer:0  
  }
},
mounted(){
  setTimeout(() => {
    this.showBlack = true
    this.startTimer()

  },this.delay)
},  

methods:{
  startTimer(){
this.timer = setInterval(() =>{
this.reactionTimer += 10
},10)
  },
  stopTimer(){
clearInterval(this.timer)
this.$emit('end',this.reactionTimer)
  }
},


updated(){
 console.log('updated');
}
}
</script>

<style>
.black{
  width: 400px;
  border-radius: 10px;
  background: rgb(14, 206, 174);
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;

}
</style>