<template>
  <svg xmlns="http://www.w3.org/2000/svg" width="300px" viewBox="0 0 250 250"><title>pyramid</title>
    <g class="big-eye">
    <polygon class="big-eye-shadow" points="125 45.62 208.93 213.37 41.08 213.37 125 45.62" fill="#141414" stroke="#141414" stroke-linecap="round" stroke-linejoin="round" stroke-width="2.5"/>
    <polygon points="125 31.41 218.64 218.59 31.36 218.59 125 31.41" fill="none" stroke="#141414" stroke-linecap="round" stroke-linejoin="round" stroke-width="2.5"/>
    <ellipse class="big-eye-blink" cx="124.49" cy="162.38" rx="52.8" ry="27.12" fill="#fff"/>
    <path d="M190.26,176.45l-11.77-23.82c-.39.69-.79,1.39-1.21,2.07a62.32,62.32,0,0,1-105.46-.24c-.42-.69-.84-1.4-1.23-2.11l-11.94,24.2a102.25,102.25,0,0,0,131.61-.1Z" fill="#fff" stroke="#141414" stroke-linecap="round" stroke-linejoin="round" stroke-width="3.5"/>
    <path d="M50.48,193.1l-9.93,20.11H76.77A98.85,98.85,0,0,1,50.48,193.1Z" fill="#fff" stroke="#141414" stroke-linecap="round" stroke-linejoin="round" stroke-width="3.5"/>
    <path d="M198.47,193.1a98.69,98.69,0,0,1-26.29,20.11H208.4Z" fill="#fff" stroke="#141414" stroke-linecap="round" stroke-linejoin="round" stroke-width="3.5"/>
    <path d="M144,128.75a60.88,60.88,0,0,1,33.33,25.95c.42-.68.82-1.38,1.21-2.07l-17.3-35a63.41,63.41,0,0,0-73.34-.2l-17.26,35c.39.71.81,1.42,1.23,2.11a60.85,60.85,0,0,1,33.37-25.77" fill="#fff"/>
    <path d="M147.85,90.58,136.53,67.66a60.68,60.68,0,0,0-12.06-1A64.5,64.5,0,0,0,112.25,68L101.13,90.5a63.81,63.81,0,0,1,46.72.08Z" fill="#fff" stroke="#141414" stroke-linecap="round" stroke-linejoin="round" stroke-width="3.5"/>
    <path d="M179.9,151.93l-17.3-35a1.53,1.53,0,0,0-.49-.58,64.95,64.95,0,0,0-75.17-.2,1.6,1.6,0,0,0-.5.59l-17.26,35a1.55,1.55,0,0,0,0,1.45c.4.73.83,1.46,1.26,2.17a1.58,1.58,0,0,0,2.69,0,59,59,0,0,1,28.55-23.68,23.1,23.1,0,0,0-2.1,9.59c0,13.2,11.19,23.93,24.94,23.93s24.94-10.73,24.94-23.93a23.07,23.07,0,0,0-2.07-9.52,59,59,0,0,1,28.52,23.84,1.57,1.57,0,0,0,1.34.75h0a1.56,1.56,0,0,0,1.34-.75c.43-.7.84-1.41,1.24-2.12A1.56,1.56,0,0,0,179.9,151.93Zm-35.47-24.68a65.52,65.52,0,0,0-39.72-.06,62.71,62.71,0,0,0-30.1,20.59l14.48-29.33a61.82,61.82,0,0,1,70.86.18l14.38,29.13A62.81,62.81,0,0,0,144.43,127.25Z" fill="#141414"/>
    <ellipse class="big-eye-blink" cx="120.14" cy="141.46" rx="8.93" ry="8.54" fill="#fff"/>
    </g>
  </svg>
</template>

<script>

export default {
  name: 'WashingtonImage'
}
</script>

 Add "scoped" attribute to limit CSS to this component only 
<style lang="scss" scoped>
  .big-eye,
  .big-eye-shadow {
    transition: transform .5s ease-in .3s;
  }

  .big-eye-blink{
    animation: blink 5s linear infinite;
  }

  @keyframes blink {
      0% { fill: none; }
      100% { fill: #fff; }
  }

  .big-eye:hover {
    transform: translate(20px, -30px);
    .big-eye-shadow {
      transform: translate(-30px, 20px);
    }
    .big-eye-blink{
      animation: none;
    }
  }
</style> 
