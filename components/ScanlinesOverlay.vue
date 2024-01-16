<template>
  <div class="scanline"></div>
</template>

<style lang="scss">
.scanline {
  background-image: url("assets/images/scanline.png");
  position: fixed;
  inset: 0;
  mix-blend-mode: soft-light;
  animation: smoothFlicker 1s infinite ease-in-out;
  @keyframes smoothFlicker {
    0% {
      opacity: 0.8;
      transform: scale(1.01);
    }
    50% {
      opacity: 0.6;
      transform: scale(1.02);
    }
    100% {
      opacity: 0.8;
      transform: scale(1.01);
    }
  }
}
</style>
