<template>
  <div>
    <div class="row">
      <div class="col right">
        <p class="right"> Do you have the answer? Make your guess below.  </p>
        <input v-model="guessAnswer" placeholder="any denomination">
        <button class="button-square">
          <p>submit</p>
        </button>
      </div>
      <div class="col">
        <EagleImage/>
      </div>
    </div>
    <div class="row">
      <div class="col">
        <button v-on:click="giveUp =! giveUp" class="button-square">
          <h3>I give up</h3>
        </button>
      </div>
      <!-- <transition name="fade"> -->
      <!-- <GameAnswer v-if="giveUp===true"/> -->
    <!-- </transition> -->
    </div>
    <transition name="fade">
    <GameAnswer v-bind:answer="8" v-if="giveUp===true"/>
    </transition>
  </div>
</template>

<script>
import GameAnswer from './GameAnswer.vue'
import EagleImage from './EagleImage.vue'

export default {
  name: 'GuessingGame',
  components: {
    GameAnswer,
    EagleImage
  },
  data: function () {
    return {
      giveUp: false,
      guessAnswer: Number
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only 
<style scoped>
/*h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}*/
</style> -->
