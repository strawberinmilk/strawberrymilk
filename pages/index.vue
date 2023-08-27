<template>
  <div :id="$style.main">
    <Transition :name="$style.strawberryAnimation">
      <StrawberryAnimation
        v-if="state.animationShow"
        :id="$style.strawberryAnimation"
      ></StrawberryAnimation>
    </Transition>
    <div v-if="state.contentsShow" :id="$style.top">
      <div :id="$style.topBox">
        <h1>strawberrymilk.dev</h1>
        <h3>ようこそ</h3>
        <p>
          <a
            ref="noreferrer noopener"
            target="_blank"
            href="https://portfolio2023.strawberrymilk.dev"
          >
            作者のページはこちら
          </a>
        </p>
        <p>
          <a href="/strawberrymilk"> いろんないちごみるく </a>
        </p>
        <el-button @click="animationReplay">アニメーションを再生</el-button>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue, { reactive } from 'vue'
import Cookies from 'universal-cookie'
import StrawberryAnimation from '~/components/StrawberryAnimation.vue'

export default Vue.extend({
  name: 'IndexPage',
  components: { StrawberryAnimation },
  setup() {
    const state = reactive({
      animationShow: false,
      contentsShow: false,
    })

    const cookies = new Cookies()

    const animationPlay = () => {
      state.animationShow = true
      setTimeout(() => {
        state.animationShow = false
        if (process.browser) cookies.set('animation_viewed', 'true')
      }, 10000)
    }

    if (process.browser && !cookies.get('animation_viewed')) {
      animationPlay()
    }

    const animationReplay = () => {
      animationPlay()
    }

    return {
      state,
      animationReplay,
    }
  },
  mounted() {
    this.state.contentsShow = true
  },
})
</script>

<style lang="scss" module>
@use '@/components/constants';

body {
  margin: 0;
}

#main {
  margin: 0;
  padding: 0;
  top: 0px;
}

#strawberryAnimation {
  position: fixed;
  margin: 0;
  padding: 0;
  z-index: 100;
}

.strawberryAnimation {
  &:global(-leave-active) {
    transition: opacity 1s;
  }

  &:global(-leave-to) {
    opacity: 0;
  }
}

#top {
  position: relative;
  height: 100vh;
  margin: 0;
  padding: 0;
}

#topBox {
  position: relative;
  width: 70%;
  height: 70%;
  left: 50%;
  top: 50%;
  padding: 20px;
  transform: translateY(-50%) translateX(-50%);
  background-color: constants.$strawberrymilk;
  text-align: center;
}
</style>
