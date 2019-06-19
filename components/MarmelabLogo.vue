<template>
  <div class="logo">
    <div class="flipper">
      <img class="front" alt="Gamepad" src="~assets/gamepad.png">
      <img class="back" alt="Marmelab" src="~assets/marmelab.png">
    </div>
  </div>
</template>

<style scoped>
.logo {
  display: inline-block;
  height: 245px;
  width: 245px;
  perspective: 1000px;
  transform: rotateY(180deg);
}

.logo .flipper {
  animation: turn 2s linear forwards 1s;
  transform: rotateY(180deg);
}

.flipper {
  transition: 0.6s;
  transform-style: preserve-3d;
  position: relative;
}

.front,
.back {
  backface-visibility: hidden;
  position: absolute;
  top: 0;
  left: 0;
  height: 245px;
  width: 245px;
}

.front {
  z-index: 2;
  /* for firefox 31 */
  transform: rotateY(0deg);
}

.back {
  transform: rotateY(180deg);
}

@keyframes turn {
  100% {
    transform: rotateY(0deg);
  }
}
</style>
