<template>
  <div class="home">
    <h1>Welcome, {{ name }}</h1>
    <router-link to="/about">About</router-link>
    <br />
    <div class="btn">
      <button>Import</button>
      <button>Export</button>
    </div>
      <button class="btn logout" @click="Logout">Logout</button>
  </div>
</template>

<script>
import { ref, onBeforeMount } from 'vue';
import firebase from 'firebase/compat/app';
export default {
  name: 'HomeView',
  setup() {
    const name = ref('');

    onBeforeMount(() => {
      const user = firebase.auth().currentUser;
      if (user) {
        name.value = user.email.split('@')[0];
      }
    });

    const Logout = () => {
      firebase
        .auth()
        .signOut()
        .then(() => console.log('Signed out'))
        .catch((err) => alert(err.message));
    };
    return {
      Logout,
      name,
    };
  },
};
</script>

<style lang="scss" scoped>
.home {
  position: absolute;
  display: block;
  text-align: center;
  width: 100%;
  max-width: 800px;
  padding: 50px 30px;
  background-image: linear-gradient(to bottom, #00bc7e, #108775);
  box-shadow: 0px 6px 12px rgba(0, 0, 0, 0.2);
  border-radius: 16px;
}

.btn button {
  display: block;
  margin: 30px auto;
  width: 150px;
  padding: 10px;
  border-radius: 8px;
  background-color: #2f4960;
  box-shadow: 0px 0px 0px rgba(0, 0, 0, 0);
  transition: 0.4s;
  color: #fff;
  font-size: 20px;
  font-weight: 700;
  cursor: pointer;
  margin-bottom: 10px;
}

.btn.logout {
  position: relative;
  left: 340px;
  bottom: 270px;
  width: 100px;
  padding: 5px;
  margin: 10px;
  color: #fff;
  font-size: 16px;
  font-weight: 500;
  cursor: pointer;
  background-color: #2f4960;
}
</style>
