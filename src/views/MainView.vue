<template>
  <div class="home">
    <h1>Welcome</h1>
    <br />
    <div class="btn">
      <button>Import</button>
      <button>Export</button>
    </div>
      <button class="btn logout" @click="Logout">Logout</button>
  </div>
</template>

<script>
export default {
  name: 'HomeView',
  methods: {
    Logout() {
      localStorage.removeItem('token');
      this.$router.push('/')
    },
  },
};
</script>

<style lang="scss" scoped>
.home {
  position: relative;
  display: block;
  text-align: center;
  width: 100%;
  max-width: 1000px;
  height: 600px;
  padding: 50px 30px;
  background-size: cover;
  background-image: url("../assets/backgroundHome.jpg");
  box-shadow: 0px 6px 12px rgba(0, 0, 0, 0.2);
  border-radius: 16px;
}

.btn button {
  display: inline-block;
  margin: 110px 10px auto;
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

.logout {
  position: absolute;
  right: 0px;
  top: 0px;
  width: 100px;
  padding: 5px;
  margin: 10px;
  color: #271b80;
  font-size: 16px;
  font-weight: 500;
  cursor: pointer;
}
.logout:hover {
  color: #000;
  transition: 0.5s;
}
</style>
