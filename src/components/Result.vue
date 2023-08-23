<template>
  <p>Reaction Time: {{ scoer }}ms</p>
  <p class="rank">{{ rank }}</p>
</template>

<script>
export default {
props:['scoer'],
data(){
    return{
        rank: null
    }
},
mounted(){
    if(this.scoer < 800){
        this.rank = "That was perfect"
    }
    else   if(this.scoer < 500){
        this.rank = "Ont bad"

    }
    else{
        this.rank = "Timer is over"

    }
}
}
</script>

<style>
.rank{
    font-size: 2.30rem;
    font-weight: bold;
    color:rgb(172, 4, 4)

}
</style>