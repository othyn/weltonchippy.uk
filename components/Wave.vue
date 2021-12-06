<template>
  <div>
    <svg
      class="waves"
      xmlns="http://www.w3.org/2000/svg"
      xmlns:xlink="http://www.w3.org/1999/xlink"
      viewBox="0 24 150 28"
      preserveAspectRatio="none"
      shape-rendering="auto"
    >
      <defs>
        <path
          id="gentle-wave"
          d="M -160 44 c 30 0 58 -8 88 -8 s 58 8 88 8 s 58 -8 88 -8 s 58 8 88 8 v 20 h -352 z"
        />
        <path
          id="small-wave"
          d="M -160 44 c 30 0 58 -13 88 -13 s 58 13 88 13 s 58 -13 88 -13 s 58 13 88 13 v 20 h -352 z"
        />
        <path
          id="medium-wave"
          d="M -160 44 c 30 0 58 -18 88 -18 s 58 18 88 18 s 58 -18 88 -18 s 58 18 88 18 v 20 h -352 z"
        />
      </defs>
      <g class="parallax">
        <use
          xlink:href="#small-wave"
          x="48"
          y="3"
          fill="rgba(255,255,255,0.2)"
        />
        <use
          xlink:href="#medium-wave"
          x="48"
          y="5"
          fill="rgba(255,255,255,0.4)"
        />
        <use
          xlink:href="#gentle-wave"
          x="48"
          y="7"
          fill="rgba(255,255,255,1)"
        />
      </g>
    </svg>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
/* Inspired by https://codepen.io/goodkatz/pen/LYPGxQz */

.parallax > use {
  animation: move-forever 60s cubic-bezier(0.55, 0.5, 0.45, 0.5) infinite;
}
.parallax > use:nth-child(1) {
  animation-delay: -1s;
  animation-duration: 20s;
}
.parallax > use:nth-child(2) {
  animation-delay: -2s;
  animation-duration: 30s;
}
.parallax > use:nth-child(3) {
  animation-delay: -3s;
  animation-duration: 40s;
}

@keyframes move-forever {
  0% {
    transform: translate3d(-90px, 0, 0);
  }
  100% {
    transform: translate3d(85px, 0, 0);
  }
}
</style>
