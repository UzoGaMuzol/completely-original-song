<template>
  <div>
    <h1>完全にオリジナルな音楽がここにあります。</h1>
    <Main />
    <a href="https://github.com/UzoGaMuzol/completely-original-song">
      Github
    </a>
  </div>
</template>

<script>
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Main
  },
  created () {
    document.title = "完全にオリジナルな音楽が聴けるサイト！！！！！！"
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
