<template>
  
    <span>
        <img :src="Micky" alt="micky mouse" class="micky">
    </span>

</template>

<script>
import Micky from "../assets/micky.png"

export default {
name:"Charachter",
data(){
    return{
        Micky
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