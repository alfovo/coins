<template>
  <!-- <div class="rotate-circle"> -->
  <div v-bind:style="{ background: coinColors[colorNum] }" class="circle">{{ denom }}</div>
  <!-- </div> -->
</template>

<script>

export default {
  name: 'CoinImage',
  props: {
    denom: Number
  },
  data: function () {
    return {
      coinColors: [
        '#daa520',
        '#cd7f32',
        '#7d7d7d',
        '#e2e3e2',
        '#905923'
      ],
    }
  },
  computed: {
    colorNum: function(){
      return Math.floor(Math.random()*5);
    }
  }
}
</script>

<style lang="scss" scoped>
  .rotate-circle{
    perspective: 100px;
    animation: blink 5s linear infinite;
  }
  .circle {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    font-size: 14px;
    font-weight: 700;
    color: #fff;
    line-height: 50px;
    text-align: center;
    margin: 5px;
  }

  @keyframes turn {
      0% { transform: rotateY(90deg); }
      50% { transform: rotateY(180deg); }
      100% { transform: rotateY(360deg); }
  }
</style> 
