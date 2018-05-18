<template>
  <div>
    <div class="row">
      <div class="col">
        <EagleArrowsImage/>
      </div>
      <div class="col">
        <p>Oh thank goodness! I don't know what I'd do without you.</p>
        <div v-if="denoms.length < 1">  
          <p>
            <label>Enter your first denomination:</label> 
            <input v-model.number="denom" type="number" placeholder="any denomination">
          </p>
        </div>
        <div v-else>
          <p>
            <label>Enter another denomination</label>
            <input v-model.number="denom" type="number" placeholder="any denomination">
        </p>
        </div>
        <div class="button-row">
          <div class="col-button">
            <button v-on:click="sumbitDenom" class="button-submit">
              <h3>submit</h3>
            </button>
          </div>
          <div class="col-button">
            <button v-on:click="clearDenoms" class="button-clear">
              <h3>clear all</h3>
            </button>
          </div>
        </div>
        <!-- <p>Your denominations: {{ denoms }}</p> -->
        <div class="row">
        <CoinImage 
          v-for="denom in denoms" :key="denom"
          v-bind:denom="denom"/>
        </div>
        </div>
      </div>
    <div v-if="denoms.length > 1" class="row">
      <div class="col">
      <div>
          <p>If you are satisfied with your denominations, enter an amount:
            <input v-model="amount" placeholder="total amount">
          </p>
        </div>
      </div>
      <div class="col">
        <button v-on:click="calculateCombinations(denoms,amount)" class="button-square">
          <h3>submit</h3>
        </button>
        <div v-if="totalCombinations">
          <p>Total combinations are: {{ totalCombinations }}</p>
        </div>
      </div>
    </div>
    <GuessingGame/>
  </div>
</template>

<script>
import GuessingGame from './GuessingGame.vue'
import EagleArrowsImage from './EagleArrowsImage.vue'
import CoinImage from './CoinImage.vue'

export default {
  name: 'GameInputs',
  components: {
    GuessingGame,
    EagleArrowsImage,
    CoinImage
  },
  props: {
    msg: String
  },
  data: function () {
    return {
      accept: true,
      denom: Number,
      denoms: [],
      amount: "",
      totalCombinations: ""
    }
  },
  methods: {
    sumbitDenom(e){
      this.denoms.push(this.denom);
      this.denom = Number;
      // make sure there's not a duplicate
      clearForm(e);
    },
    clearDenoms: function() {
      this.denoms = [];
    },
    clearForm(e) {
      this.denom = Number;
      this.amount = "";
      e.preventDefault();
    },
    calculateCombinations: function(denoms, amount){
      this.totalCombinations = amount + 3;
    }
  }
}
</script>