<template>
  
    <span>
        <img :src="Micky" alt="micky mouse" class="micky" @click="stopTime"  v-if="showimg" :style="{top:top + 'px',left:left+'px',right:right+'px',bottom:bottom+'px'}">
    </span>

</template>

<script>
import Micky from "../assets/micky.png"

export default {
name:"Charachter",
props:["delay"],
data(){
    return{
        Micky,
        showimg:false,
        timer: null,
        reactiontime:0,
        left:Math.random()*150,
        top:Math.random()*200,
        right:Math.random()*180,
        bottom:Math.random()*220
    }

},

mounted (){
    setTimeout(()=>{
        this.showimg=true;
        this.startTime();
    },this.delay)

},

methods: {

    startTime(){
        this.timer= setInterval(()=> {
            this.reactiontime+=10
        }, 10)
    },

    stopTime(){
        clearInterval(this.timer);
        this.$emit("endgame",this.reactiontime);
    }

}


}


</script>

<style scoped>

.micky {
    position: relative;
    width:100px;
    height: 150px;
}


</style>