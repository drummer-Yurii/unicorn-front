<template>
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
  background: #2c3e50;
  color: #fff;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
}
</style>
