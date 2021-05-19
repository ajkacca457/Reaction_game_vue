<template>
  <h4>Your Reaction time is : {{score}}</h4>
  <p class="score">{{rank}}</p>
</template>

<script>
export default {
name:"Result",
props:["score"],
data(){
  return {
    rank:null
  }
},

mounted(){

if(this.score<400){
  this.rank="You are Faster than the flash!! You are Super Flash."
} else if( this.score<800){
  this.rank="You are fast but Flash will kick your butt. You are HawkEye."
} else if(this.score>800){
  this.rank="Are you here to play?? why are you even trying!!. You are Whiplash."
}

}

}
</script>

<style scoped>

.score {
  background-color: brown;
  color:yellow;
  width:60%;
  margin: 0 auto;
  padding:5px;
}

</style>