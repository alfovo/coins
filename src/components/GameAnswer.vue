<template>
<div>
  <div class="row">
      <div class="col">
        <BigEyeImage/>
      </div>
    </div>
  <div class="row">
      <div class="col">
        <p>You have displeased the great eye! </p>
        <p>The great eye is not attatched to a brain and therefore has a lot of trouble working these things out.</p>
        <p>But just in case you were curious, the answer is: <b>{{ answer }}</b>.</p>
      </div>
  </div>
</div>
</template>

<script>
import BigEyeImage from './BigEyeImage.vue'

export default {
  name: 'GameAnswer',
  components: {
    BigEyeImage
  },
  props: {
    answer: Number
  },
  data: function () {
    return {
      accept: true,
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
