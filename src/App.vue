<template>
  <div id="app">
    <WashingtonImage/>
    <Introduction v-bind:msg="quotes[quoteNum]"/>
  
    <div class="row">
      <div class="col">
        <button v-on:click="accept =! accept" class="button-square">
          <h3 v-if="accept">I've changed my mind</h3>
          <h3 v-else>Yes, I will help you</h3>
        </button>
      </div>
    </div>
    <transition name="fade">
      <GameInputs v-if="accept===true"/>
    </transition>
  </div>
</template>

<script>
import Introduction from './components/Introduction.vue'
import GameInputs from './components/GameInputs.vue'
import WashingtonImage from './components/WashingtonImage.vue'

export default {
  name: 'app',
  components: {
    Introduction,
    GameInputs,
    WashingtonImage
  },
  data: function () {
    return {
      quotes: [
        'Hello, my precocious numismatist friend...',
        'If money go before, all ways do lie open',
        'It costs a lot of money to look this cheap',
        'Be the change that you wish to see in the world.',
        'Money, money, money -- must be funny'
      ],
      accept: false
    }
  },
  computed: {
    quoteNum: function(){
      return Math.floor(Math.random()*4);
    }
  }

}
</script>
