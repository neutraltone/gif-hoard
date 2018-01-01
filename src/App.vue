<template>
  <div id="app">
    <header>
      <span>GifHoarder</span>
    </header>
    <main>
      <img src="./assets/logo.png" alt="Vue.js PWA">
      <router-view></router-view>
    </main>
  </div>
</template>

<script>
export default {
  name: 'app',
};
</script>

<style>
body {
  margin: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #ff0099;
}

main {
  margin: 1em 0;
  text-align: center;
}

header {
  margin: 1em 0;
  text-align: center;
  font-size: 2.5em;
}
</style>
