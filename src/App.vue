<template>
  <div id="app">
    <router-view />
  </div>
</template>

<style lang="scss">
@import './style/reset.css';

#app {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
    Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

body {
 width: 100vw;
 height: 100vh;
}
</style>
