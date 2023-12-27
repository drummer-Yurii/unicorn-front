<template>
  <div class="logo">
    <img src="./assets/flag.jpg" alt="logo" />
    <p class="title1">simple</p>
    <p class="title2">choice</p>
  </div>
  <router-view/>
</template>
<script>
import { onBeforeMount } from 'vue';
import { useRoute, useRouter } from 'vue-router';
import firebase from 'firebase/compat/app';
export default {
  setup() {
    const router = useRouter();
    const route = useRoute();

    const auth = firebase.auth();

    onBeforeMount(() => {
      auth.onAuthStateChanged((user) => {
        if (!user) {
          router.replace('/login');
        } else if (route.path == '/login' || route.path == '/register') {
          router.replace('/');
        }
      });
    });
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Fira sans', sans-serif;
}

body {
  background-image: url('./assets/bg.png');
  color: #fff;
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
  background: rgba(44, 62, 80, 0.7);
}

.logo {
  position: absolute;
  top: 20px;
  left: 20px;
  width: 200px;
}

.logo img {
  border-radius: 30px;
  width: 100%;
}

.title1 {
  position: absolute;
  top: 20px;
  left: 40px;
  color: yellow;
  font-size: 30px;
  font-weight: bold;
  font-style: italic;
  text-transform: uppercase;
}

.title2 {
  position: absolute;
  top: 80px;
  left: 40px;
  color: blue;
  font-size: 30px;
  font-weight: bold;
  font-style: italic;
  text-transform: uppercase;
}
</style>
