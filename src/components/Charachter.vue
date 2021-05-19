<template>
  
    <span>
        <img :src="Micky" alt="micky mouse" class="micky" @click="stopTime"  v-if="showimg">
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
        reactiontime:0
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
    width:150px;
    height: 200px;
}


</style>