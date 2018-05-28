<template>
  <div>
    <div class="row">
      <div class="col">
        <EagleArrowsImage/>
      </div>
      <div class="col">
        <h4>Oh thank goodness! I don't know what I'd do without you.</h4>
        <p>
          Let’s consider currency in the United States. We have a base unit, called a dollar, made up of 100 subunits called cents. 
          Each coin, called a denomination, represents a certain number of cents. For our purposes, let’s assume each coin is less than 100 cents. 
          Can you come up with at least two denominations?
        </p>
      </div>
    </div>
    <div class="row">
      <div class="col primary">
        <h4>
          <label>{{ denomMessage }}: </label> 
          <input v-model.number="denom" type="number" placeholder="0">
          ¢
        </h4>
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
        <br>
        <p>
          Great! Can you enter a total number of dollars? 
          Remember, each dollar represents 100 cents. 
          For our purposes, let’s only use whole numbers for amount.
        </p>
        <h4>
          <label>Enter a total amount: </label>
          <input v-model="amount" placeholder="0">
          dollars
        </h4>
        <!-- <div class="button-row">
            <button v-on:click="calculateCombinations(denoms,amount)" class="button-submit">
              <h3>submit your currency</h3>
            </button>
        </div> -->
      </div>
      <div class="col">
        <div class="row">
          <CoinImage 
          v-for="denom in denoms" :key="denom"
          v-bind:denom="denom"/>
        </div>
        <div v-if="amount">
        $ {{ amount }}.00
        </div>
      </div>
    </div>
    <div class="row">
      <div class="button-row">
            <button v-on:click="calculateCombinations(denoms,amount)" class="button-square">
              <h3>submit your coin collection</h3>
            </button>
        </div>
    </div>
    <GuessingGame v-if="totalCombinations"/>
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
  computed:{
    denomMessage: function() {
      if(this.denoms < 1){
        return 'Enter your first denomination'
      }
      else {
        return 'Enter another denomination'
      }
    }
  },
  methods: {
    sumbitDenom(e){
      this.denoms.push(this.denom + " ¢");
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