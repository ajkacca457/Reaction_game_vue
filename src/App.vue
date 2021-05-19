<template>
  <div class="Game">
  <Navbar/>
  <button class="btn" @click="play" :disabled="isPlay">Start</button>
  <div class="display">
  <Charachter v-if="isPlay"/>
  </div>
  </div>

</template>

<script>
import Navbar from "./components/Navbar.vue"
import Charachter from "./components/Charachter.vue"



export default {
  name: 'App',
  components: {
    Navbar,
    Charachter
  },
  data(){
    return{
      delay:null,
      isPlay:false
    }

  },

  methods: {

    play(){
      this.isPlay=true;
      this.delay= 2000+Math.random()*5000;
      console.log(this.delay)
      console.log(this.isPlay)

    }
  }

}
</script>

<style>
#app {
  text-align: center;
}
.btn {
  width:20%;
  padding:5px 8px;
}


.display {
  width: 100%;
  height: 100%;
  padding:3% 0;
 
}

</style>
