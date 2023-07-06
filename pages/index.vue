<template>
  <div :id="$style.main">
    <div :id="$style.top">
      <h1>strawberrymilk.dev</h1>
      <h3>🚧WIP Page🚧</h3>
      <p>
        <a
          ref="noreferrer noopener"
          target="_blank"
          href="https://portfolio2023.strawberrymilk.dev"
        >
          作者のページはこちら
        </a>
      </p>
      <!--
      <p>
        <a
          target="_blank"
          ref="noreferrer noopener"
          href="https://twitter.com/strawbeRinMilk"
        >
          Twitter
        </a>
      </p>
      <p>
        <a
          target="_blank"
          ref="noreferrer noopener"
          href="https://qiita.com/strawbeRinMilk"
        >
          Qiita
        </a>
      </p>
      <p>
        <a
          target="_blank"
          ref="noreferrer noopener"
          href="https://github.com/strawberinmilk"
        >
          GitHub
        </a>
      </p>
      -->
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
})
</script>

<style module>
#main {
  position: relative;
  width: 100vw;
  height: 100vh;
}
#top {
  position: relative;
  width: 70%;
  height: 70%;
  left: 50%;
  top: 50%;
  padding: 20px;
  transform: translateY(-50%) translateX(-50%);
  background-color: rgb(255, 154, 255);

  text-align: center;
}
</style>
