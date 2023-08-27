<template>
  <div :id="$style.main">
    <div :id="$style.bottleBack"></div>
    <img :id="$style.milk" src="/milk.png" />
    <div :id="$style.milkBack"></div>
    <div>
      <img :class="$style.strawberry" src="/strawberry.png" />
      <img :class="$style.strawberry" src="/strawberry.png" />
      <img :class="$style.strawberry" src="/strawberry.png" />
      <img :class="$style.strawberry" src="/strawberry.png" />
    </div>
    <div :id="$style.logoParent">
      <div :class="$style.logo_band"></div>
      <div :id="$style.logoText">
        <h1>strawberrymilk.dev</h1>
      </div>
      <div :class="$style.logo_band"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'StrawberryAnimation',
}
</script>

<style lang="scss" module>
@use '@/components/constants';

#main {
  position: fixed;
  height: 100vh;
  width: 100vh;
  margin: 0;
  top: 0px;
}

#bottleBack {
  position: fixed;
  height: 100vh;
  width: 100vw;
  bottom: 0px;
  left: 0px;
  z-index: 0;
  background-color: rgb(127, 225, 255);
}

#milk {
  position: fixed;
  z-index: 10;
  width: 300px;
  top: 0px;
  left: calc(50vw - 150px);
  animation-name: milk_animation;
  animation-duration: 10s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
}

@keyframes milk_animation {
  0% {
    transform: rotate(0deg);
  }
  10% {
    transform: rotate(-60deg);
  }
  25% {
    top: 0px;
    transform: rotate(-75deg);
  }
  40% {
    top: -300px;
    transform: rotate(-180deg);
  }
  100% {
    top: -300px;
    transform: rotate(-90deg);
  }
}

#milkBack {
  position: fixed;
  width: 100vw;
  bottom: 0px;
  left: 0px;
  z-index: 0;
  background-color: white;

  animation-name: milk_back_animation;
  animation-duration: 10s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
}

@keyframes milk_back_animation {
  10% {
    height: 0vh;
  }
  50% {
    height: 100vh;
  }
  60% {
    background-color: white;
  }
  70% {
    background-color: constants.$strawberrymilk;
  }
  100% {
    height: 100vh;
    background-color: constants.$strawberrymilk;
  }
}

.strawberry {
  position: fixed;
  z-index: 10;
  width: 150px;
  top: -200px;

  animation-name: strawberry_animation;
  animation-duration: 10s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
}

.strawberry:nth-child(1) {
  left: calc(75px);
}
.strawberry:nth-child(2) {
  left: calc(25% + 75px);
}
.strawberry:nth-child(3) {
  left: calc(50% + 75px);
}
.strawberry:nth-child(4) {
  left: calc(75% + 75px);
}

@keyframes strawberry_animation {
  50% {
    top: -200%;
  }
  60% {
    top: 25vh;
    opacity: 1;
  }
  70% {
    opacity: 0;
  }
  100% {
    top: 25vh;
    opacity: 0;
  }
}

#logoParent {
  position: fixed;
  height: 50vh;
  width: 100vw;
  top: 25vh;
  left: 0px;
  z-index: 10;
}

.logo_band {
  position: relative;
  height: 10vh;
  width: 0vw;
  background-color: white;
  animation-duration: 10s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
}

.logo_band:first-child {
  animation-name: logo_band_top_animation;
  left: 0vw;
}

.logo_band:last-child {
  animation-name: logo_band_bottom_animation;
  left: 100vw;
}

@keyframes logo_band_top_animation {
  70% {
    width: 0vw;
  }
  80% {
    width: 100vw;
  }
  100% {
    width: 100vw;
  }
}

@keyframes logo_band_bottom_animation {
  70% {
    left: 100vw;
    width: 0vw;
  }
  80% {
    left: 0vw;
    width: 100vw;
  }
  100% {
    left: 0vw;
    width: 100vw;
  }
}

#logoText {
  position: relative;
  height: 30vh;
  text-align: center;
  opacity: 0;
  background-color: rgb(195, 227, 255);
  animation-name: logo_text_animation;
  animation-duration: 10s;
  animation-iteration-count: 1;
  animation-fill-mode: forwards;
}

@keyframes logo_text_animation {
  80% {
    opacity: 0;
  }
  90% {
    opacity: 1;
  }
  100% {
    opacity: 1;
  }
}

#logoText h1 {
  position: relative;
  margin: 0;
  padding: 0;
  line-height: 30vh;
}
</style>
