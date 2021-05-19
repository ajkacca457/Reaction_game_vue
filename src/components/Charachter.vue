<template>
  
    <span>
        <img :src="Micky" alt="micky mouse" class="micky" @click="check" v-if="showimg">
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
        showimg:false
    }

},

methods:{
    check(){
        console.log(this.delay)
    }
},

mounted (){
    setTimeout(()=>{
        this.showimg=true
    },this.delay)

}


}


</script>

<style scoped>

.micky {
    width:150px;
    height: 200px;
}


</style>