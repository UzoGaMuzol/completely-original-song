<template>
  <div>
    <h1>完全にオリジナルな音楽がここにあります。</h1>
    <p class="description">
      世間で知られている音楽はパクリだらけで酷いと思いませんか？ 
      でも大丈夫！ このサイトでは、<strong>完全にオリジナルな</strong>
      音楽を、<strong>誰でも無料で</strong>お楽しみいただけます！
    </p>
    <img src="./assets/musicnote.png" alt="music note" width="200" class="mb-3">
    <Main />
    <ul class="links">
      <li>
        <a href="https://github.com/UzoGaMuzol/completely-original-song">
          <i class="bi bi-github"></i>
          Github
        </a>
      </li>
      <li>
        <a href="https://twitter.com/uzogamuzol">
          <i class="bi bi-twitter"></i>
          Twitter
        </a>
      </li>
    </ul>
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

.description {
  max-width: 500px;
  margin: 0 auto;
  text-align: left;
}
ul.links {
  list-style-type: none;
}

ul.links li {
  display: inline;
  margin-right: 1em
}
</style>
