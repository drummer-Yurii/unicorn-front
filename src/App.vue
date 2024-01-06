<template>
  <router-view />
</template>
<script>
export default {
  setup() {},
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Fira sans", sans-serif;
  font-size: 18px;
}

body {
  background: #e4eafe;
  color: #271b80;
}

#app {
  position: relative;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  background: #e4eafe;
}
</style>
