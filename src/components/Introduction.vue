<template>
  <div class="row">
    <div class="col">
      <h1>{{ msg }}</h1>
      <p>
        Say, can you help me sort through my coin collection? I've been meaning to solve this riddle: 
      </p>
      <p id="riddle">
      Given a set of coin denominations and a total amount, can you count how many combinations of coins you can use to make that total amount? 
      </p>
      <p>
      For example, United States currency has 0.01, 0.05, 0.10, 0.25 and 1.00 denominations currently. You can use X combinations of those denominations to make a dollar! Please help me, I'm <i>counting</i> on you.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Introduction',
  props: {
    msg: String
  }
}
</script>