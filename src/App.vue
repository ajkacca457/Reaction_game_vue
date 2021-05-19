<template>
  <div class="Game">
  <Navbar/>
  <button class="btn" @click="play" :disabled="isPlay">Start</button>
  <Result :score="score" v-if="showscore"/>
  <div class="display">
  <Charachter v-if="isPlay" :delay="delay" @endgame="end"/>
  </div>
  </div>

</template>

<script>
import Navbar from "./components/Navbar.vue"
import Charachter from "./components/Charachter.vue"
import Result from "./components/Result.vue"



export default {
  name: 'App',
  components: {
    Navbar,
    Charachter,
    Result
  },
  data(){
    return{
      delay:null,
      isPlay:false,
      score:null,
      showscore:false
    }

  },

  methods: {

    play(){
      this.isPlay=true;
      this.delay= 1000+Math.random()*3000;
      this.showscore=false;
    },

    end(score){
      this.score=score;
      this.isPlay=false;
      this.showscore=true;
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
  height: 60vh;
  padding:3% 0;
  position: relative;
 
}

</style>
